# Database Documentation - Moral Survey System

## 1. Database Overview

### 1.1 System Information
- **Database Type:** MongoDB (NoSQL)
- **TypeORM Version:** Latest
- **Node.js Framework:** NestJS
- **Primary Database Names:**
  - `posts` - Reddit posts data and questions
  - `survey` - Survey responses and user answers
  - `cache` - Application cache storage
  - `reddit` - Reddit metadata

### 1.2 Architecture Overview

The system uses a microservice architecture with MongoDB as the primary data store, utilizing TypeORM for object-document mapping.

```
┌──────────────────────────────────┐
│     Frontend Application         │
├──────────────────────────────────┤
│      NestJS API Gateway          │
├──────────────────────────────────┤
│     TypeORM Data Access Layer    │
├──────────────────────────────────┤
│      MongoDB Database Cluster    │
└──────────────────────────────────┘
```

### 1.3 Database Connections

| Connection Name | Database | Purpose |
|----------------|----------|---------|
| posts | posts | Reddit post data and questions |
| survey | survey | User survey responses |
| cache | cache | Application caching |

## 2. Collections Schema

### 2.1 Collection: `posts` (Question Entity)
**Database:** posts
**Purpose:** Stores Reddit AITA (Am I The Asshole) posts for survey questions

| Field | Type | Constraints | Description |
|-------|------|-------------|-------------|
| _id | string | PRIMARY KEY | Reddit post ID |
| title | string | NOT NULL | Post title |
| selftext | string | NOT NULL | Post content/body |
| very_certain_YA | number | NOT NULL | Percentage very certain "You're the Asshole" |
| very_certain_NA | number | NOT NULL | Percentage very certain "Not the Asshole" |
| YA_percentage | number | NOT NULL | Overall YA percentage |
| NA_percentage | number | NOT NULL | Overall NA percentage |
| original_post_YA_top_reasonings | string[] | NOT NULL | Top YA reasoning comments |
| original_post_NA_top_reasonings | string[] | NOT NULL | Top NA reasoning comments |
| count | number[] | NOT NULL | Vote distribution array |

**Indexes:**
- PRIMARY KEY on `_id`
- Text index on `title` and `selftext` for search

### 2.2 Collection: `all` (PostMateData Entity)
**Database:** posts
**Purpose:** Comprehensive Reddit post metadata and analytics

| Field | Type | Description |
|-------|------|-------------|
| _id | string | Primary key |
| year | int | Post year |
| month | int | Post month |
| day | int | Post day |
| verdict | string | Final verdict (YTA/NTA/ESH/NAH) |
| num_words | int | Word count in post |
| label_entropy | double | Verdict certainty measure |
| score | int | Reddit score |
| YTA | int | "You're the Asshole" votes |
| NTA | int | "Not the Asshole" votes |
| ESH | int | "Everyone Sucks Here" votes |
| NAH | int | "No Assholes Here" votes |
| INFO | int | "Need More Info" votes |
| title | string | Post title |
| topic_1 | string | Primary topic |
| topic_1_p | double | Primary topic probability |
| topic_2 | string | Secondary topic |
| topic_2_p | double | Secondary topic probability |
| topic_3 | string | Tertiary topic |
| topic_3_p | double | Tertiary topic probability |
| topic_4 | string | Quaternary topic |
| year_r | int | Response year |
| month_r | int | Response month |
| day_r | int | Response day |
| hour | int | Response hour |
| minute | int | Response minute |
| second | int | Response second |
| num_words_r | int | Response word count |
| num_comments | int | Total comments |
| score_r | int | Response score |
| flair | string | Post flair |
| verdict_r | string | Response verdict |
| resolved_verdict | string | Final resolved verdict |
| v_id | string | Verdict ID |
| v_year | int | Verdict year |
| v_month | int | Verdict month |
| v_day | int | Verdict day |
| v_hour | int | Verdict hour |
| v_minute | int | Verdict minute |
| v_second | int | Verdict second |
| v_words | int | Verdict word count |
| v_score | int | Verdict score |

### 2.3 Collection: `post_summary` (PostSummary Entity)
**Database:** posts
**Purpose:** Summarized post information for quick access

| Field | Type | Description |
|-------|------|-------------|
| id | string | Primary key |
| title | string | Post title |
| verdict | string | Final verdict |
| YTA | number | YTA vote count |
| NTA | number | NTA vote count |
| selftext | string | Post content |
| commentCount | number | Number of comments |
| topics | string[] | Associated topics |

### 2.4 Collection: `answer` (Answer Entity)
**Database:** survey
**Purpose:** Complete survey responses from participants

| Field | Type | Constraints | Description |
|-------|------|-------------|-------------|
| _id | string | PRIMARY KEY | MongoDB ObjectId |
| prolificId | string | NOT NULL | Prolific platform user ID |
| studyId | number | NOT NULL | Study identifier |
| answerDetail | AnswerItem[] | NOT NULL | Array of question answers |
| comment | string | NULLABLE | General comment |
| decisionMaking | number[] | NOT NULL | 25-item decision scale |
| personalityChoice | number[] | NOT NULL | 15-item personality scale |
| time | bigint | NOT NULL | Completion timestamp |

**Nested Type: AnswerItem**
| Field | Type | Description |
|-------|------|-------------|
| _id | ObjectId | Item identifier |
| questionId | string | Reference to Question |
| individualAnswer | Object | Personal judgment |
| groupAnswer | Object | Group consensus |
| comment | string | Question-specific comment |

**Answer Object Structure:**
| Field | Type | Description |
|-------|------|-------------|
| isAsshole | boolean | Asshole determination |
| rating | number (1-5) | Severity rating |

### 2.5 Collection: `prolifics` (Prolific Entity)
**Database:** survey
**Purpose:** Participant demographic and platform data

| Field | Type | Constraints | Description |
|-------|------|-------------|-------------|
| _id | ObjectId | AUTO | MongoDB ObjectId |
| prolificId | string | PRIMARY KEY | Unique participant ID |
| age | number | NOT NULL | Participant age |
| country | string | NOT NULL | Country of origin |
| frequentUser | boolean | NOT NULL | Reddit usage frequency |
| language | string | NOT NULL | Primary language |
| takenBefore | boolean[] | NOT NULL | Previous survey participation (5 studies) |
| visitSubreddit | boolean | NOT NULL | AITA subreddit familiarity |

### 2.6 Collection: `MoralCache` (Cache Entity)
**Database:** cache
**Purpose:** Application-level caching

| Field | Type | Description |
|-------|------|-------------|
| _id | ObjectId | MongoDB ObjectId |
| key | string | Cache key (PRIMARY) |
| value | string | Cached value (JSON) |
| expiresAt | Date | Expiration timestamp |
| hit | number | Cache hit counter |

## 3. Data Relationships

### 3.1 Entity Relationships

```mermaid
erDiagram
    Question ||--o{ AnswerItem : references
    PostMateData ||--|| PostSummary : summarizes
    Prolific ||--o{ Answer : submits
    Answer ||--|{ AnswerItem : contains

    Question {
        string _id PK
        string title
        string selftext
        number YA_percentage
        number NA_percentage
    }

    Answer {
        string _id PK
        string prolificId FK
        number studyId
        AnswerItem[] answerDetail
        number[] decisionMaking
        number[] personalityChoice
    }

    Prolific {
        string prolificId PK
        number age
        string country
        boolean frequentUser
    }

    AnswerItem {
        ObjectId _id
        string questionId FK
        object individualAnswer
        object groupAnswer
    }
```

### 3.2 Reference Mappings

| Parent Collection | Child Collection | Relationship | Foreign Key |
|-------------------|-----------------|--------------|-------------|
| Question | AnswerItem | One-to-Many | questionId |
| Prolific | Answer | One-to-Many | prolificId |
| Answer | AnswerItem | One-to-Many | Embedded |
| PostMateData | PostSummary | One-to-One | id/_id |

## 4. Indexes and Performance

### 4.1 Index Strategy

| Collection | Index Name | Fields | Type | Purpose |
|------------|------------|--------|------|---------|
| posts | _id_idx | _id | Primary | Primary key lookup |
| posts | title_text | title, selftext | Text | Full-text search |
| all | date_composite | year, month, day | Compound | Date range queries |
| all | verdict_idx | verdict | Single | Verdict filtering |
| answer | prolific_study | prolificId, studyId | Compound | User study lookup |
| prolifics | prolificId_idx | prolificId | Unique | User identification |
| MoralCache | key_idx | key | Unique | Cache key lookup |
| MoralCache | expires_idx | expiresAt | Single | Expiration cleanup |

### 4.2 Query Optimization Guidelines

1. **Use projection** to limit returned fields
2. **Implement pagination** for large result sets
3. **Use aggregation pipeline** for complex queries
4. **Cache frequently accessed data**
5. **Monitor slow query logs**

## 5. Data Types and Validation

### 5.1 Enum Values

**Verdict Types:**
- `YTA` - You're the Asshole
- `NTA` - Not the Asshole
- `ESH` - Everyone Sucks Here
- `NAH` - No Assholes Here
- `INFO` - Need More Information

**Rating Scale:**
- 1 - Not at all
- 2 - Slightly
- 3 - Moderately
- 4 - Very
- 5 - Extremely

### 5.2 Validation Rules

| Entity | Field | Validation |
|--------|-------|------------|
| Answer | rating | Min: 1, Max: 5 |
| Answer | decisionMaking | Array length: 25 |
| Answer | personalityChoice | Array length: 15 |
| Answer | isAsshole | Boolean required |
| Prolific | takenBefore | Array length: 5 |

## 6. API Integration

### 6.1 Connection Configuration

```typescript
// MongoDB Connection Configuration
{
  type: 'mongodb',
  url: process.env.DATABASE_URL,
  database: 'posts|survey|cache',
  logging: true,
  entities: [Entity Classes],
  migrations: ['src/migration/**/*.ts'],
  migrationsTableName: 'migrations'
}
```

### 6.2 Environment Variables

| Variable | Description | Example |
|----------|-------------|---------|
| DATABASE_URL | MongoDB connection string | mongodb://user:pass@host:27017 |
| DB_NAME | Database name | posts |
| DB_LOGGING | Enable query logging | true |
| CONNECTION_POOL_SIZE | Max connections | 10 |

## 7. Data Migration

### 7.1 Migration Strategy

Migrations are managed through TypeORM migration system:

```bash
# Generate migration
npm run migration:generate -- -n MigrationName

# Run migrations
npm run migration:run

# Revert migration
npm run migration:revert
```

### 7.2 Migration Files Location
- Path: `src/migration/**/*.ts`
- Table: `migrations` (tracking table)

## 8. Security Considerations

### 8.1 Access Control

1. **Authentication:** Prolific ID validation
2. **Authorization:** Study-based access control
3. **Data Privacy:** No PII stored except Prolific ID
4. **Encryption:** TLS for data in transit

### 8.2 Data Retention Policy

| Data Type | Retention Period | Action |
|-----------|-----------------|---------|
| Survey Responses | Indefinite | Archive after study |
| Cache Data | Dynamic (expiresAt) | Auto-delete |
| User Demographics | Study duration | Anonymize post-study |

## 9. Backup and Recovery

### 9.1 Backup Strategy

| Backup Type | Frequency | Retention |
|-------------|-----------|-----------|
| Full Backup | Daily | 30 days |
| Incremental | Every 6 hours | 7 days |
| Replica Set | Real-time | 3 replicas |

### 9.2 Recovery Procedures

```bash
# MongoDB backup
mongodump --uri="mongodb://..." --out=/backup/$(date +%Y%m%d)

# MongoDB restore
mongorestore --uri="mongodb://..." --dir=/backup/20250928

# Point-in-time recovery using oplog
mongorestore --uri="mongodb://..." --oplogReplay --oplogLimit="timestamp"
```

## 10. Monitoring and Maintenance

### 10.1 Key Metrics

| Metric | Warning Threshold | Critical Threshold |
|--------|------------------|-------------------|
| Connection count | 80% of pool | 95% of pool |
| Query response time | > 500ms | > 2000ms |
| Database size | 70% capacity | 85% capacity |
| Cache hit rate | < 60% | < 40% |

### 10.2 Maintenance Tasks

```javascript
// Clear expired cache
db.MoralCache.deleteMany({ expiresAt: { $lt: new Date() } })

// Compact collections
db.runCommand({ compact: 'posts' })

// Update statistics
db.posts.reIndex()

// Check collection sizes
db.posts.stats()
```

## 11. Sample Queries

### 11.1 Common Operations

```javascript
// Find questions by verdict
db.posts.find({ verdict: "YTA" }).limit(10)

// Get user's answers
db.answer.find({ prolificId: "user123" })

// Aggregate verdict distribution
db.all.aggregate([
  { $group: {
    _id: "$verdict",
    count: { $sum: 1 },
    avgScore: { $avg: "$score" }
  }}
])

// Cache lookup with TTL check
db.MoralCache.findOne({
  key: "cache_key",
  expiresAt: { $gt: new Date() }
})
```

### 11.2 Complex Aggregations

```javascript
// Topic analysis by verdict
db.all.aggregate([
  { $match: { verdict: { $in: ["YTA", "NTA"] } } },
  { $group: {
    _id: {
      verdict: "$verdict",
      topic: "$topic_1"
    },
    count: { $sum: 1 },
    avgEntropy: { $avg: "$label_entropy" }
  }},
  { $sort: { count: -1 } }
])

// User participation statistics
db.answer.aggregate([
  { $lookup: {
    from: "prolifics",
    localField: "prolificId",
    foreignField: "prolificId",
    as: "userInfo"
  }},
  { $unwind: "$userInfo" },
  { $group: {
    _id: "$userInfo.country",
    participants: { $sum: 1 },
    avgCompletionTime: { $avg: "$time" }
  }}
])
```

## 12. Troubleshooting

### 12.1 Common Issues

| Issue | Symptoms | Solution |
|-------|----------|----------|
| Connection timeout | "MongoTimeoutError" | Check network, increase timeout |
| Duplicate key | "E11000 duplicate key" | Check unique indexes |
| Out of memory | Process crash | Increase Node.js heap size |
| Slow queries | High response time | Add indexes, optimize queries |

### 12.2 Diagnostic Commands

```javascript
// Check current operations
db.currentOp()

// View collection statistics
db.posts.stats()

// Analyze query performance
db.posts.find({}).explain("executionStats")

// Check index usage
db.posts.aggregate([
  { $indexStats: {} }
])
```

## 13. Data Dictionary

### 13.1 Naming Conventions

| Pattern | Example | Description |
|---------|---------|-------------|
| Collections | lowercase_snake | post_summary |
| Fields | camelCase | prolificId |
| Indexes | collection_field_idx | posts_verdict_idx |
| Foreign keys | entityId | questionId, prolificId |

### 13.2 Data Standards

| Type | MongoDB Type | Description |
|------|--------------|-------------|
| ID | String/ObjectId | Unique identifiers |
| Boolean | Boolean | True/false values |
| Integer | Int32/Int64 | Whole numbers |
| Float | Double | Decimal numbers |
| Timestamp | Date/Number | Time values |
| Array | Array | List values |
| JSON | Object | Nested documents |

## 14. Compliance and Ethics

### 14.1 Research Ethics
- IRB approval required for human subjects research
- Informed consent obtained via Prolific
- Data anonymization implemented
- No direct PII collection

### 14.2 GDPR Compliance
- Right to access: Export user data by prolificId
- Right to deletion: Remove participant records
- Data minimization: Only collect necessary data
- Purpose limitation: Use only for research 