# Delivery Plan
**Course:** COMP8715
**Group:** Moral Decisions
**Delivery Phase:** Weeks 10-12
**Last Updated:** October 7, 2025 (Tuesday, Week 10)

## 1. Executive Summary

This delivery plan outlines the comprehensive approach for delivering all project documentation, system components, and demonstration materials to stakeholders during Weeks 10-12. The plan has been developed through active consultation with our tutor and client stakeholders during Week 10, and will be enacted during Weeks 10-12 with final delivery in Week 12. This document serves as the formal Delivery Plan required for assessment (20% of Delivery phase grade).

## 2. Deliverables Summary

| Deliverable | Format | Draft Completion | Draft Review | Final Completion | Final Submission |
|------------|--------|-----------------|--------------|------------------|------------------|
| Product Demonstration Video | MP4 (2-3 min) | Oct 12 (Sat) | Oct 13 (Mon) | Oct 19 (Sat) | Oct 20 (Mon) |
| System Architecture Document | PDF + Markdown | Oct 12 (Sat) | Oct 13 (Mon) | Oct 19 (Sat) | Oct 20 (Mon) |
| API Documentation | PDF + HTML | Oct 12 (Sat) | Oct 13 (Mon) | Oct 19 (Sat) | Oct 20 (Mon) |
| Deployment Guide | PDF + Markdown | Oct 12 (Sat) | Oct 13 (Mon) | Oct 19 (Sat) | Oct 20 (Mon) |
| Database Documentation | PDF + Markdown | Oct 12 (Sat) | Oct 13 (Mon) | Oct 19 (Sat) | Oct 20 (Mon) |
| Maintenance Manual | PDF + Markdown | Oct 12 (Sat) | Oct 13 (Mon) | Oct 19 (Sat) | Oct 20 (Mon) |
| Source Code & LandingSite | GitHub Repository | Continuous | Oct 13 (Mon) | Oct 19 (Sat) | Oct 20 (Mon) |
| Handover Package | Complete Folder | - | - | Oct 19 (Sat) | Oct 20 (Mon) |

**Key Dates:**
- **Week 10 (Oct 6-12):** Complete all documentation and video drafts
- **Week 11 Monday (Oct 13):** Present all drafts to stakeholder and receive feedback
- **Week 11 (Oct 13-19):** Finalize all deliverables based on stakeholder feedback
- **Week 12 Monday (Oct 20):** Final delivery and handover to stakeholder and tutor

**Note:** All meeting minutes and project documentation are maintained in the LandingSite repository (LandingSite/25S2/), not as separate deliverables.

## 3. Detailed Deliverable Requirements

### 3.1 Product Demonstration Video
**Format:** Screen recording video (MP4)
**Duration:** 2-3 minutes
**Target Draft Completion:** October 12, 2025 (Saturday, Week 10)
**Draft Demo:** October 13, 2025 (Monday, Week 11)
**Target Final Completion:** October 19, 2025 (Saturday, Week 11)
**Final Submission:** October 20, 2025 (Monday, Week 12)

**Purpose:**
Visual demonstration showing how to run the product and showcase the complete user workflow through the web application.

**Required Content:**

**Part 1: System Launch (30-45 seconds)**
- Show terminal/command prompt
- Display and execute commands to start each component in order:
  - Backend server startup command
  - Frontend application startup command
- Show successful startup messages in terminal
- Display the URL to access the application

**Part 2: Web Application User Flow (1.5-2 minutes)**
- Open web browser and navigate to application URL
- Demonstrate complete user click flow through the website:
  - **Home Page**: Show the main page, browse posts/games
  - **Survey Page**: Navigate to and demonstrate survey functionality

**Quality Criteria:**
- All features clearly visible and demonstrated
- Smooth, professional recording
- Clear demonstration of functionality
- No sensitive data or credentials visible
- Properly paced (not too fast or slow)
- Focus on terminal commands and user click flow only

### 3.2 System Architecture Document
**Format:** PDF + Markdown source
**Target Draft Completion:** October 12, 2025 (Saturday, Week 10)
**Draft Demo:** October 13, 2025 (Monday, Week 11)
**Target Final Completion:** October 19, 2025 (Saturday, Week 11)
**Final Submission:** October 20, 2025 (Monday, Week 12)

**Purpose:**
Document the current system architecture as inherited and modified by the team.

**Required Contents:**

1. **System Overview** (1 page)
   - Brief description of the Moral Decisions project
   - Project objectives and scope

2. **Architecture Diagrams** (2-3 pages)
   - High-level system architecture showing major components
   - Component interactions and data flow
   - Frontend-backend-database relationships

3. **Technology Stack** (1 page)
   - Frontend: List technologies used 
   - Backend: List technologies used 
   - Database: Database type and structure
   - Deployment: Hosting and infrastructure overview

4. **Database Overview** (1 page)
   - List of all databases used in the system
   - Purpose of each database
   - Database technology/type for each

5. **API Structure** (1 page)
   - Overview of API endpoints
   - Brief description of main API routes
   - Authentication approach (if applicable)

**Note:** Detailed database connection, modification, and content information is covered in the separate Database Documentation (Section 3.5).

**Quality Criteria:**
- Clear diagrams showing system components
- Accurate representation of current system
- Professional formatting

### 3.3 API Documentation
**Format:** PDF + HTML (optional)
**Target Draft Completion:** October 12, 2025 (Saturday, Week 10)
**Draft Demo:** October 13, 2025 (Monday, Week 11)
**Target Final Completion:** October 19, 2025 (Saturday, Week 11)
**Final Submission:** October 20, 2025 (Monday, Week 12)

**Purpose:**
Document the existing API endpoints for future developers and stakeholders.

**Required Contents:**

1. **API Overview** (1 page)
   - Brief description of API purpose
   - Base URL
   - Authentication approach (if any)

2. **Endpoint Documentation** (3-5 pages)
   For each major endpoint:
   - HTTP Method and URL path
   - Brief description
   - Request parameters (if any)
   - Response format example
   - Common error responses

3. **Data Models** (1-2 pages)
   - Key data structures used in API
   - Field descriptions
   - Example JSON objects

**Quality Criteria:**
- All main endpoints documented
- Clear examples provided
- Accurate information

### 3.4 Deployment Guide
**Format:** PDF + Markdown source
**Target Draft Completion:** October 12, 2025 (Saturday, Week 10)
**Draft Demo:** October 13, 2025 (Monday, Week 11)
**Target Final Completion:** October 19, 2025 (Saturday, Week 11)
**Final Submission:** October 20, 2025 (Monday, Week 12)

**Purpose:**
Provide step-by-step instructions for deploying the application.

**Required Contents:**

1. **System Requirements** (1 page)
   - Required software and versions
   - Operating system requirements
   - Hardware recommendations

2. **Installation Steps** (2-3 pages)
   - Clone repository command
   - Install dependencies command
   - Database setup steps
   - Environment configuration (.env file setup)

3. **Running the Application** (1-2 pages)
   - Commands to start backend
   - Commands to start frontend
   - How to access the application
   - Default ports and URLs

4. **Common Issues** (1 page)
   - Typical deployment problems and solutions
   - Port conflicts
   - Database connection issues

**Quality Criteria:**
- Clear step-by-step instructions
- All commands provided and tested
- Easy to follow for someone unfamiliar with the project

### 3.5 Database Documentation
**Format:** PDF + Markdown source
**Target Draft Completion:** October 12, 2025 (Saturday, Week 10)
**Draft Demo:** October 13, 2025 (Monday, Week 11)
**Target Final Completion:** October 19, 2025 (Saturday, Week 11)
**Final Submission:** October 20, 2025 (Monday, Week 12)

**Purpose:**
Comprehensive documentation of all databases used in the system, including connection methods, modification procedures, and content descriptions. This is a critical stakeholder requirement.

**Required Contents:**

1. **Database Overview** (1 page)
   - List of all databases in the system
   - Purpose and role of each database
   - Database technologies used 

2. **Database Connection Information** (2-3 pages)

   For each database, document:
   - **Connection String Format**
     - Host and port information
     - Database name
     - Authentication requirements
   - **Connection Setup Steps**
     - How to establish connection from code
     - Required credentials and environment variables
   - **Connection Examples**
     - Code snippets showing how to connect
     - Common connection issues and solutions

3. **Database Content Documentation** (3-5 pages)

   For each database, document:
   - **Complete Schema/Structure**
     - All tables/collections listed
     - Field/column names and data types
     - Primary keys and foreign keys
     - Indexes and constraints
   - **Data Descriptions**
     - Purpose of each table/collection
     - Description of each field/column
     - Sample data or examples
     - Data relationships and dependencies

**Quality Criteria:**
- Complete coverage of all databases
- Clear step-by-step connection instructions
- Detailed modification procedures that can be followed by someone unfamiliar with the system
- Comprehensive content documentation for each database
- Accurate and tested information

### 3.6 Maintenance Manual
**Format:** PDF + Markdown source
**Target Draft Completion:** October 12, 2025 (Saturday, Week 10)
**Draft Demo:** October 13, 2025 (Monday, Week 11)
**Target Final Completion:** October 19, 2025 (Saturday, Week 11)
**Final Submission:** October 20, 2025 (Monday, Week 12)

**Purpose:**
Provide guidance for ongoing system maintenance and troubleshooting.

**Required Contents:**

1. **System Overview** (1 page)
   - Brief system description
   - Key components that require maintenance

2. **Regular Maintenance Tasks** (1-2 pages)
   - Recommended maintenance schedule
   - Database backup procedures
   - Log file management
   - Dependency updates

3. **Common Issues and Solutions** (2-3 pages)
   - Application not starting (causes and fixes)
   - Performance issues (causes and fixes)
   - Database connection problems (causes and fixes)
   - Common error messages and their meanings

4. **Contact Information** (1 page)
   - Team contact details
   - Repository and documentation links

**Quality Criteria:**
- Practical and actionable guidance
- Clear troubleshooting steps
- Useful for future maintainers

### 3.7 Handover Package
**Format:** Complete folder structure
**Target Completion:** October 19, 2025 (Saturday, Week 11)
**Final Submission:** October 20, 2025 (Monday, Week 12)

**Purpose:**
Organize all deliverables in a structured format for easy access and handover to stakeholders.

**Package Structure:**
```
/Moral_Decisions_Final_Delivery/
├── README.txt                                  # Package overview and navigation guide
│
├── /01_Video/
│   └── Product_Demonstration.mp4               # 2-3 minute demo video
│
├── /02_Documentation/
│   ├── System_Architecture.pdf
│   ├── API_Documentation.pdf
│   ├── Deployment_Guide.pdf
│   ├── Database_Documentation.pdf              # Detailed database info
│   ├── Maintenance_Manual.pdf
│   └── Delivery_Plan.pdf                       # This document
│
├── /03_Source_Files/
│   ├── System_Architecture.md
│   ├── API_Documentation.md
│   ├── Deployment_Guide.md
│   ├── Database_Documentation.md
│   └── Maintenance_Manual.md
│
└── /04_Repository_Access/
    ├── GitHub_Repository_Info.txt              # Main repository URL
    ├── LandingSite_Access_Guide.txt            # How to access LandingSite documentation
    └── Repository_Structure.txt                # Overview of repository organization
```

**Quality Criteria:**
- Well-organized folder structure
- All files properly named and formatted
- README provides clear navigation
- Repository access information is complete and accurate
- Easy for stakeholders to access all materials

## 4. Stakeholder Consultation

### Key Stakeholders
- **External Stakeholder (Client):** Primary recipient of deliverables and provides project requirements
- **Project Tutor:** Academic oversight and assessment
- **Development Team:** Implementation and documentation

### Consultation Process

#### Week 10 Consultation Activities (October 6-12, 2025 - Current Week):
- **Monday, October 6:**
  - 8-hour collective work session at Hive
  - Tutor meeting at 11:00 AM: Delivery Plan initial discussion
  - Client meeting at 12:00 PM: Requirements gathering and validation
  - Afternoon: Begin documentation development

- **Tuesday-Saturday, October 7-12:**
  - Continuous communication via Teams/WeChat
  - Intensive work on all documentation drafts
  - Complete all documentation first drafts by Saturday, October 12
  - Obtain formal approval of Delivery Plan

#### Week 11 Consultation (October 13-19, 2025):
- **Monday, October 13:**
  - 8-hour collective work session at Hive
  - **Tutor meeting at 11:00 AM:** Review all documentation drafts, receive feedback
  - **Client meeting at 12:00 PM:** Present all draft deliverables, discuss revisions
  - Afternoon: Incorporate feedback and finalize revisions

- **Tuesday-Sunday, October 14-19:**
  - Finalize all documentation based on client feedback
  - Polish and quality assurance review
  - Prepare final delivery package
  - Continuous communication via Teams/WeChat

#### Week 12 Final Delivery (October 20-26, 2025):
- **Monday, October 20:**
  - 8-hour final session at Hive
  - **Final Tutor Meeting (11:00 AM):** Formal delivery and assessment
  - **Final Client Meeting (12:00 PM):** Stakeholder presentation and handover
  - Knowledge transfer session
  - Project closure

- **Tuesday-Saturday, October 21-26:**
  - Post-delivery support
  - Response to follow-up questions
  - Stakeholder evaluation completion

### Consultation Evidence
- Meeting minutes from all consultations (stored in GitHub)
- Signed approval of Delivery Plan (bottom of document)

## 5. Delivery Timeline

### Work Schedule Overview
- **Primary Work Day:** Every Monday, 8 hours at Hive (9:00 AM - 5:00 PM)
- **Tutor Meeting:** Every Monday, 11:00 AM (30 minutes)
- **Stakeholder Meeting:** Every Monday, 12:00 PM (30 minutes)
- **Remote Work:** Tuesday-Sunday (as needed)

### Week 10 - Documentation Development Sprint (October 6-12, 2025 - CURRENT WEEK)

**Monday, October 6 (8-hour session at Hive):**
- 9:00 AM - 10:30 AM: Delivery Plan development and team alignment
- 11:00 AM - 11:30 AM: **Tutor Meeting** - Delivery Plan discussion
- 12:00 PM - 12:30 PM: **Client Meeting** - Requirements validation
- 1:00 PM - 1:30 PM: Lunch break
- 1:30 PM - 4:30 PM: Begin documentation development (Architecture, API, Deployment)
- 4:30 PM - 5:00 PM: Task distribution and sprint planning

**Tuesday, October 7 (Remote work) - TODAY:**
- Continue System Architecture Document development
- Begin API Documentation
- Start Deployment Guide outline

**Wednesday-Friday, October 8-10 (Remote work):**
- Complete System Architecture diagrams and content
- Complete API Documentation with all endpoints
- Complete Deployment Guide with step-by-step procedures
- Complete Maintenance Manual with checklists
- Develop User Manual (if applicable)
- Prepare Test Documentation

**Saturday-Sunday, October 11-12 (Final push):**
- **Deliverable Complete:** System Architecture Document (Draft)
- **Deliverable Complete:** API Documentation (Draft)
- **Deliverable Complete:** Deployment Guide (Draft)
- **Deliverable Complete:** Maintenance Manual (Draft)
- **Deliverable Complete:** Test Documentation (Draft)
- **Deliverable Complete:** Product Demonstration Video
- Quality assurance review of all drafts
- Package all deliverables for Monday presentation

### Week 11 - Client Review and Finalization (October 13-19, 2025)

**Monday, October 13 (8-hour session at Hive) - CRITICAL REVIEW DAY:**
- 9:00 AM - 10:30 AM: Team preparation for client presentation
- 11:00 AM - 11:30 AM: **Tutor Meeting** - Present all draft deliverables
- 12:00 PM - 12:30 PM: **Client Meeting** - Present all drafts, gather feedback and requirements
- 1:00 PM - 1:30 PM: Lunch break
- 1:30 PM - 5:00 PM: Document client feedback, prioritize revisions, begin implementing changes

**Tuesday-Friday, October 14-17 (Remote work):**
- Incorporate all client and tutor feedback
- Finalize all documentation revisions
- Update video if needed based on feedback
- Test all procedures and validate accuracy
- Peer review and quality checks

**Saturday-Sunday, October 18-19:**
- Final polish of all deliverables
- Complete final delivery package assembly
- Prepare presentation for Week 12 final delivery
- Final quality assurance check

### Week 12 - Final Delivery and Handover (October 20-26, 2025)

**Monday, October 20 (Final 8-hour session at Hive):**
- 9:00 AM - 10:30 AM: Final preparation and team practice
- 10:30 AM - 11:00 AM: Pre-delivery verification checklist
- 11:00 AM - 12:00 PM: **Final Tutor Meeting** - Formal delivery and assessment
- 12:00 PM - 1:00 PM: **Final Client Meeting** - Stakeholder presentation and handover
- 1:00 PM - 1:30 PM: Lunch break
- 1:30 PM - 3:00 PM: Knowledge transfer session
- 3:00 PM - 4:00 PM: Q&A and clarifications
- 4:00 PM - 5:00 PM: Project closure and team retrospective

**Tuesday-Saturday, October 21-26:**
- Post-delivery support period
- Response to follow-up questions (within 24 hours)
- Minor documentation updates if requested
- Stakeholder evaluation completion support
- Final project archival

## 6. Assessment Alignment

This Delivery Plan aligns with the TechLauncher 2025 S2 Delivery Assessment Guide rubric for **teams with an external stakeholder**:

### Delivery Plan (20%)
- Developed in consultation with stakeholder and tutor during Week 10
- Clear deliverables with specific deadlines
- Comprehensive handover procedures
- Communication strategy defined

### Delivery Execution (50%)
- All deliverables planned for completion by deadlines
- Full handover package prepared
- Regular consultations with stakeholder and tutor
- Quality assurance processes in place

### Stakeholder Evaluation (30%)
- Regular stakeholder meetings (every Monday)
- Stakeholder involved in draft review (Week 11 Monday)
- Stakeholder feedback incorporated
- Final stakeholder evaluation in Week 12

## 7. Quality Assurance

### Documentation Standards
- Consistent formatting across all documents
- Professional presentation
- Version control via GitHub
- Peer review within team

### Review Process
1. **Team Review:** Internal checking for completeness and accuracy
2. **Draft Review (Week 11 Monday):** Present to stakeholder and tutor for feedback
3. **Final Review:** Incorporate all feedback before Week 12 delivery

### Acceptance Criteria
- All deliverables complete and accurate
- Stakeholder feedback incorporated
- Professional quality
- Meets assessment requirements

## 8. Handover Package Structure

Refer to Section 3.9 for the complete handover package structure.

### Delivery Methods
- **Primary:** Google Drive link shared with stakeholder and tutor
- **Backup:** USB drive (if requested)
- **Code Access:** GitHub repository access
- **Presentation:** In-person handover during Week 12 Monday

## 9. Risk Management

| Risk | Mitigation Strategy |
|------|---------------------|
| Delayed stakeholder feedback | Submit drafts early, maintain buffer time |
| Team member unavailability | Cross-training, clear task distribution |
| Technical issues with deliverables | Test early, have backup plans |
| Time constraints | Prioritize tasks, focus on essential content |

## 10. Communication Plan

### Communication Channels
- **Team Coordination:** Teams / WeChat group
- **Document Sharing:** GitHub + Google Drive
- **In-Person:** Every Monday at Hive (8 hours)

### Meeting Schedule
- **Monday 11:00 AM:** Tutor Meeting (30 min)
- **Monday 12:00 PM:** Stakeholder Meeting (30 min)
- **Monday 9:00 AM - 5:00 PM:** Team work session at Hive

## 11. Project Closure

### Handover Checklist
- [ ] All documentation delivered
- [ ] Product demonstration video delivered
- [ ] Source code repository accessible
- [ ] Meeting minutes compiled
- [ ] Stakeholder sign-off obtained
- [ ] Tutor assessment completed

### Week 12 Monday Closure Activities (October 20)
- **11:00 AM:** Final tutor meeting and assessment
- **12:00 PM:** Final stakeholder meeting and handover
- **Afternoon:** Knowledge transfer and Q&A
- **End of day:** Project closure and team retrospective

---

## Approval and Consultation Confirmation

**Approval Signatures:**

_Client Representative:_ _________________________ Date: _________

_Project Tutor:_ ________________________________ Date: _________

_Team Representative:_ ___________________________ Date: _________

---

**Consultation Confirmation:**

This Delivery Plan has been developed through consultation with our external stakeholder and project tutor during Week 10. The plan reflects agreed requirements and expectations for project delivery during Weeks 10-12, aligning with TechLauncher 2025 S2 Delivery Assessment Guide.

**Key Milestone Dates:**
- **Week 10 (Oct 6-12):** Delivery Plan consultation and draft development
  - Monday Oct 6: Initial stakeholder and tutor meetings (Hive)
  - Saturday Oct 12: All draft deliverables completed
- **Week 11 (Oct 13-19):** Draft review and finalization
  - Monday Oct 13: Present all drafts to stakeholder and tutor (Hive)
  - Oct 13-19: Incorporate feedback and finalize all deliverables
- **Week 12 (Oct 20-26):** Final delivery and handover
  - Monday Oct 20: Final delivery to stakeholder and tutor (Hive)
  - Oct 20-26: Post-delivery support


