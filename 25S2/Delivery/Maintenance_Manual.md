# Maintenance Manual

**Project:** Moral Decisions
**Team:** Moral Decisions 
**Version:** 1.0
**Date:** 12/10/2025
**Authors:** Lingziluo Xiong

---

## Table of Contents
1. [System Overview](#1-system-overview)
2. [Regular Maintenance Tasks](#2-regular-maintenance-tasks)
3. [Common Issues and Solutions](#3-common-issues-and-solutions)
4. [Contact Information](#4-contact-information)

---

## 1. System Overview

### 1.1 System Description
The Moral Decisions project supports “AI + Human Exploration of Daily Moral Decisions” via two interactive websites:
- **Moral Profile Website:** Scenario-based moral mini-games (inspired by online forums) to help users explore common moral dilemmas.
- **Opinion Survey Website:** Collects real moral choices and generates personalized feedback reports based on decision patterns.

The goal is to leverage AI–human collaboration to build a data-driven platform for everyday, nuanced moral reasoning, creating a scalable foundation for ethical AI research.

Tech stack and deployment highlights (from the LandingSite repo and linked resources):

Deployment: Azure Web App (Docker supported)
Frontend: Next.js (with API Routes; index page may directly access DB to simplify backend)
Backend: NestJS (separate from frontend; interacts via REST API)
API: Two key endpoints
Deliver survey questions by studyId
Receive survey responses by prolificId (documentation also mentions “profilicId”; use actual implementation in code)
Version Control: Git (GitHub)
Dev environment: Unified via server + Docker
Testing: Postman for API testing
Audience and impact:

Users: Global participants
Beneficiaries: Researchers in AI ethics, moral psychology, and social computing
Client: Ziyu Chen (Computational Media Lab)
Reference repository:
https://github.com/24-S1-2-C-Moral-Decisions/LandingSite

### 1.2 Key Components
- **Frontend:** Next.js 
- - Provides UI/UX for Moral Profile and Opinion Survey
- - Uses Next.js API Routes for some data reads (especially index), reducing backend overhead
- - May include SSR/ISR and build cache (.next)

- **Backend:** NestJS
- - Decoupled from frontend; exposes REST APIs
- - Communicates with frontend via API calls
  
- **Database:** MangoDB

- **API:** 
  GET /api/survey?studyId=<ID>: returns survey by studyId
  POST /api/response: accepts responses with prolificId/profilicId and answer payload
  Actual paths/params must follow code in the repos
  
- **Deployment:** 
  Azure Web App (Linux), container-friendly
  Environment variable management (PORT, DATABASE_URL, etc.)

- **Tooling:**
  Git (GitHub)
  Docker (local and/or cloud images)
  Postman (API testing)

### 1.3 Components Requiring Maintenance
- [Component 1 and maintenance requirements]
- [Component 2 and maintenance requirements]
- [Component 3 and maintenance requirements]

---

## 2. Regular Maintenance Tasks

### 2.1 Maintenance Schedule Overview

| Frequency | Tasks | Estimated Time |
|-----------|-------|----------------|
| Daily | [Task list] | [Time] |
| Weekly | [Task list] | [Time] |
| Monthly | [Task list] | [Time] |
| Quarterly | [Task list] | [Time] |

---

### 2.2 Daily Maintenance Tasks

#### Task 2.2.1: Check System Health
**Frequency:** Daily
**Estimated Time:** 5-10 minutes
**Priority:** High

**Steps:**
1. [Step 1]
2. [Step 2]
3. [Step 3]

**Expected Results:**
- [Expected result 1]
- [Expected result 2]

**What to do if issues found:**
- [Action 1]
- [Action 2]

---

#### Task 2.2.2: Review Error Logs
**Frequency:** Daily
**Estimated Time:** 10-15 minutes
**Priority:** High

**Steps:**
1. Access log files at `[log-file-location]`
2. Check for errors or warnings
3. Review critical errors
4. Document any recurring issues

**Expected Results:**
- No critical errors
- Normal application warnings only

**What to do if issues found:**
- [Troubleshooting steps]

---

### 2.3 Weekly Maintenance Tasks

#### Task 2.3.1: Database Backup
**Frequency:** Weekly (Every Monday at [time])
**Estimated Time:** 15-20 minutes
**Priority:** Critical

**Steps:**
1. [Step 1]
2. [Step 2]
3. [Step 3]

**Backup Location:**
```
[Backup directory path]
```

**Backup Commands:**
```bash
[Backup command]
```

**Verification:**
```bash
[Verification command]
```

---

#### Task 2.3.2: Log File Management
**Frequency:** Weekly
**Estimated Time:** 10 minutes
**Priority:** Medium

**Steps:**
1. Check log file sizes at `[log-directory]`
2. Archive logs older than [X days]
3. Delete logs older than [X months]
4. Verify log rotation is working

**Log Locations:**
- Application logs: `[path]`
- Error logs: `[path]`
- Access logs: `[path]`

**Commands:**
```bash
# Check log sizes
du -sh [log-directory]/*

# Archive old logs
[archive-command]

# Delete old logs
[delete-command]
```

---

#### Task 2.3.3: Dependency Updates Check
**Frequency:** Weekly
**Estimated Time:** 15 minutes
**Priority:** Medium

**Steps:**
1. Check for security updates
2. Review update changelog
3. Test updates in development environment
4. Schedule update deployment if needed

**Commands:**
```bash
# Check for npm updates
npm outdated

# Check for security vulnerabilities
npm audit
```

---

### 2.4 Monthly Maintenance Tasks

#### Task 2.4.1: Full System Health Review
**Frequency:** Monthly (First Monday of month)
**Estimated Time:** 30-45 minutes
**Priority:** High

**Steps:**
1. [Step 1]
2. [Step 2]
3. [Step 3]

---

#### Task 2.4.2: Database Optimization
**Frequency:** Monthly
**Estimated Time:** 20-30 minutes
**Priority:** Medium

**Steps:**
1. Analyze database performance
2. Rebuild indexes if needed
3. Clean up orphaned data
4. Verify database integrity

**Commands:**
```bash
[Database optimization commands]
```

---

#### Task 2.4.3: Security Review
**Frequency:** Monthly
**Estimated Time:** 30 minutes
**Priority:** High

**Steps:**
1. Review access logs for suspicious activity
2. Check security patches available
3. Review user access permissions
4. Update firewall rules if needed

---

## 3. Common Issues and Solutions

### 3.1 Application Not Starting

**Symptoms:**
- [Symptom 1]
- [Symptom 2]

**Possible Causes:**
1. [Cause 1]
2. [Cause 2]
3. [Cause 3]

**Diagnosis Steps:**
```bash
# Step 1: Check if process is running
[check-command]

# Step 2: Check logs
[log-command]

# Step 3: Verify configuration
[verify-command]
```

**Solutions:**

**Solution 1: [Solution Name]**
```bash
[Solution commands or steps]
```

**Solution 2: [Solution Name]**
```bash
[Solution commands or steps]
```

**Prevention:**
- [Prevention measure 1]
- [Prevention measure 2]

---

### 3.2 Performance Issues

**Symptoms:**
- Slow response times
- High CPU usage
- High memory usage

**Possible Causes:**
1. [Cause 1]
2. [Cause 2]
3. [Cause 3]

**Diagnosis Steps:**
```bash
# Check system resources
top
# or
htop

# Check application performance
[performance-check-command]

# Check database performance
[database-check-command]
```

**Solutions:**

**Solution 1: Clear Cache**
```bash
[Cache clearing steps]
```

**Solution 2: Restart Application**
```bash
[Restart commands]
```

**Solution 3: Scale Resources**
[Steps to scale resources]

**Prevention:**
- Regular monitoring
- Scheduled restarts
- Resource optimization

---

### 3.3 Database Connection Problems

**Symptoms:**
- "Cannot connect to database" errors
- Timeout errors
- Authentication failures

**Possible Causes:**
1. Database service not running
2. Wrong credentials
3. Network connectivity issues
4. Connection pool exhausted

**Diagnosis Steps:**
```bash
# Check database service status
[status-check-command]

# Test database connection
[connection-test-command]

# Check database logs
[log-command]
```

**Solutions:**

**Solution 1: Restart Database Service**
```bash
[Restart command]
```

**Solution 2: Verify Credentials**
```bash
[Verification steps]
```

**Solution 3: Check Network**
```bash
[Network diagnostic commands]
```

**Prevention:**
- Monitor database health
- Regular backups
- Connection pool configuration

---

### 3.4 Common Error Messages

#### Error: "[Error Message 1]"
**Meaning:** [What this error means]
**Cause:** [Common cause]
**Solution:** [Solution steps]

#### Error: "[Error Message 2]"
**Meaning:** [What this error means]
**Cause:** [Common cause]
**Solution:** [Solution steps]

#### Error: "[Error Message 3]"
**Meaning:** [What this error means]
**Cause:** [Common cause]
**Solution:** [Solution steps]

---

## 4. Contact Information

### 4.1 Team Contact Details

**Primary Contact:**
- Name: [Name]
- Email: [email]
- Phone: [phone]
- Availability: [availability]

**Secondary Contact:**
- Name: [Name]
- Email: [email]
- Phone: [phone]
- Availability: [availability]

**Team Email:** [team-email]

---

### 4.2 Stakeholder Contact Information

**Client/Stakeholder:**
- Name: [Name]
- Organization: [Organization]
- Email: [email]
- Phone: [phone]

---

### 4.3 Repository and Documentation Links

**Main Repository:**
- GitHub: [repository-url]
- Branch: [main-branch]

**LandingSite Documentation:**
- Location: `LandingSite/25S2/`
- Meeting Minutes: `LandingSite/25S2/Minutes/`
- Deliverables: `LandingSite/25S2/Delivery/`

**Other Documentation:**
- System Architecture: [link]
- API Documentation: [link]
- Database Documentation: [link]
- Deployment Guide: [link]

---

### 4.4 Emergency Contacts

**For Critical Issues (System Down, Security Breach):**
1. Contact: [Primary contact]
2. If unavailable: [Secondary contact]
3. Escalation: [Escalation contact]

**Support Hours:**
- Regular support: [hours]
- Emergency support: [availability]

---

## Appendix: Maintenance Checklists

### Daily Checklist
- [ ] Check system health
- [ ] Review error logs
- [ ] Monitor system resources
- [ ] Verify backups completed (if scheduled)

### Weekly Checklist
- [ ] Perform database backup
- [ ] Manage log files
- [ ] Check for dependency updates
- [ ] Review security logs
- [ ] Test backup restoration (monthly sample)

### Monthly Checklist
- [ ] Full system health review
- [ ] Database optimization
- [ ] Security review
- [ ] Update documentation if needed
- [ ] Review and update this manual

---

## Quality Checklist
- [ ] Practical and actionable guidance
- [ ] Clear troubleshooting steps
- [ ] Useful for future maintainers
- [ ] All contact information accurate
- [ ] All sections complete
- [ ] Reviewed by team
