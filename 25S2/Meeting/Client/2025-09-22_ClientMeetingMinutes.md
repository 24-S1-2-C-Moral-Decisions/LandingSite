# Meeting Minutes

## Meeting Information

**Meeting Date/Time:** 22/09/2025 (Week 8)  
**Meeting Purpose:** Client meeting, update progress on DB–Survey integration, display video, and logic documentation  
**Meeting Location:** Hive  
**Note Taker:** Lingziluo Xiong

## Attendees

People who attended: Client and all team members

## Agenda Items  

**Database Update (Survey UI ↔ Database)**

- Clarify end-to-end data flow from Survey UI to database.  
- List all databases, their schemas, and hosting locations (e.g., MongoDB vs Nectar instance).  
- Provide step-by-step procedure for editing survey content and persisting changes to the database.

**Display Website Video**

- Record a short demo showing how to run the website locally and access it publicly.  
- Include a full survey submission and verification that data is saved and can be queried.

**Logic Documentation**

- Produce logic docs explaining product/system logic and architecture:  
  - Front-end hooks → API contracts → backend handlers → database operations.  
  - Validation/decision rules and data processing.  
  - Include diagrams and concise examples.

**Deployment**

- Ensure both local and public environments are available for demo and verification.

---

## Discussion Items  

| Item                  | Notes                                              |
| --------------------- | -------------------------------------------------- |
| Update database       | Define Survey UI → API/validation → DB write → readback; confirm DB host/location and ownership. |
| Deploy                | Demonstrate local run and public URL; show submission and DB verification with a simple query. |
| Documentation & video | Logic doc focuses on architecture and relationships; organize by feature (Survey) and by layers. |

---

## Client Suggestions  
1. Provide a clear, actionable guide for Survey UI ↔ Database integration.  
2. Record a display video that demonstrates the complete data loop: submit → store → query.  
3. Deliver logic documentation covering front end, backend, and database for each feature.

---

## Other Notes  

- Prioritize architecture and logic relationships over low-level code details.  
- No user manual required at this stage; focus on Survey + Database first.

---

## Next Week Deliverables Confirmation  
1. Survey–Database integration documented with DB inventory, schemas, data flow diagram, and step-by-step update procedure.  
2. Local and public deployments available with URLs and health checks; display video recorded showing a full submission and data read.  
3. Initial logic documentation delivered in GitHub (/docs) and linked from README.
