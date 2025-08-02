# Reflection Logs

**Date:** 02/08/2025

---

### Overall Progress Overview

During Sprint 4 of 2025, our team focused on re-establishing our data infrastructure. Key achievements include:

- **Database Rebuild:** Successfully provisioned a new MongoDB instance to replace the expired database.
- **Data Import:** Cleaned, transformed, and imported the latest dataset into the new database, ensuring schema compatibility and data integrity.
- **Connection Validation:** Updated application configurations to point to the new database and verified end-to-end connectivity through automated smoke tests.

---

### Analysis of Successful Experiences

Our efforts during this Sprint highlighted several strengths:

- **Data Quality Practices:** By applying data validation scripts before import, we caught inconsistencies early and maintained high data integrity.
- **Automated Testing:** Incorporating smoke tests into the CI pipeline allowed us to quickly detect and resolve any connection or import issues, boosting confidence in the new setup.

---

### Challenges

- **Lack of Technical Documentation:** This project spans four semesters without a formal documentation repository, making knowledge transfer difficult.
- **No Handover Process:** Previous team members did not provide a structured handover, resulting in gaps in system understanding.
- **Expired MongoDB Instance:** The original database expired unexpectedly, forcing an urgent rebuild and import plan under time pressure.

---

### Improvement Strategy

- **Establish Documentation Standards:** Create and maintain up-to-date technical documents, including database schemas, deployment steps, and environment configurations.
- **Automate Backup and Monitoring:** Set up regular automated backups and monitoring alerts for the MongoDB instance to prevent future expirations and detect anomalies early.

---

### Next Steps

- **Documentation Drive:** Assign team members to document existing systems.
- **Backup Configuration:** Configure and test backups and retention policies for the new MongoDB deployment.

