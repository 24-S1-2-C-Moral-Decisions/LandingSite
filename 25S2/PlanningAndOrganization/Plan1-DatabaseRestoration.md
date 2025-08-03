# Planning and Organization Logs

## Planning Details 
- Date: July 28, 2025
- Planning Maker: All Members

## Background 
After returning from the holiday, we discovered that the backend database was down. In addition, the new survey data from the client has not yet been provided. During our internal discussions and the meeting with the client, several questions arose regarding:
- Whether modifications had been made to the database in the past
- If the database sessions (or credentials) might be expiring due to inactivity
- The recurring connection timeouts for the survey, cache, and post databases  
This critical issue required immediate action to restore the database’s functionality and ensure system stability.

## Planning Options 
The team considered the following options to address the database disruption:

- **Option 1:** Use the available "all" JSON file to set up a local database instance and execute migration scripts. This would restore the database (including survey, cache, and post tables) using the known migration logic (similar to the previous categories migration).
- **Option 2:** Update the database connection by modifying the environment configuration (env file) to point to the Nectar database instead of the old Azure-based API. This option involves minimal changes since the schema is unchanged.
- **Option 3:** Run diagnostic scripts to verify connectivity across all databases and identify if the issues are due to expired sessions or network restrictions (e.g., VPN issues).

## Planning Rationale 
The team decided that the most efficient approach was to:
- First, restore the database using the existing JSON file and migration scripts.
- Then, update the environment configuration to change the database address to the Nectar database.
  
This approach minimizes code changes, as the API logic remains largely the same (only the connection address needs updating), and it quickly restores service functionality while providing a clear path to test the migrated data.

## Planning Outcome 
We decided to:
1. **Restore the Database:**  
   - Run the migration using the "all" JSON file to ensure that all tables (survey, cache, and post) are properly set up.
2. **Update Environment Configuration:**  
   - Change the database address in the `env` file to point from the prior Azure connection to the Nectar database.
3. **Conduct Connectivity Tests:**  
   - Verify both the front end and back end to ensure data (especially posts) loads correctly.
4. **Track the Issue:**  
   - Open and monitor a GitHub issue in the backend repository to address and trace the ongoing database connection timeout problems.

## Implementation Plan 

1. **Database Restoration:**
   - **Task:** Use the "all" JSON file to set up a local MongoDB instance and execute migration scripts.
   - **Action:** Run the migration to restore survey, cache, and post tables.
   - **Responsible:** Zihao Li and Yu Ma
   - **Resources:** Migration scripts, JSON data file.

2. **Environment Update:**
   - **Task:** Update the database address in the `env` file to reflect the Nectar database.
   - **Action:** Deploy and test the updated configuration to ensure connectivity.
   - **Responsible:** Lingziluo Xiong
   - **Resources:** Updated configuration files.

3. **Connectivity Testing:**
   - **Task:** Execute tests on both the front end and back end to verify that the database restoration was successful.
   - **Action:** Check API endpoints to confirm that post data loads correctly.
   - **Responsible:** Shutong Li
   - **Resources:** Testing protocols and logs.

4. **Issue Tracking:**
   - **Task:** Open and manage an issue in the backend repository regarding the persistent database connection timeouts.
   - **Action:** Document observations and update the issue with test results.
   - **Responsible:** Fei Li
   - **Resources:** GitHub Issues, team feedback.

## Risks and Mitigation 

1. **Risk:** Failure of the migration script to restore all required data.
   - **Mitigation:** Create a backup of the current data, and run the migration in a controlled environment to validate the process.

2. **Risk:** Updating the environment variable might not fully resolve connection issues if there are compatibility problems with Nectar.
   - **Mitigation:** Perform thorough testing across development and staging environments before final deployment.

3. **Risk:** Delayed receipt of the new survey data from the client.
   - **Mitigation:** Proceed with restoration using existing data and schedule a follow-up with the client for updated data submissions.

## Follow-up Actions 

1. Monitor the performance and connectivity of the Nectar database in both development and production settings.
2. Schedule a review of the migration and configuration update process.
3. Confirm with the client the status and expected delivery date of the new survey data.
4. Update the GitHub issue with test outcomes and any further adjustments needed.

## Table of Decisions (Summary)

| Decision                                      | Outcome                                                                               | Date         |
| --------------------------------------------- | ------------------------------------------------------------------------------------- | ------------ |
| Restore database using JSON migration         | Run migration script to restore survey, cache, and post tables using the JSON data.   | Jul 28, 2025 |
| Update environment to use Nectar database     | Only update the database address in the env file, keeping API logic unchanged.         | Aug 01, 2025 |
| Open backend issue for connection timeouts      | Track and document ongoing timeouts for further investigation in GitHub Issues.         | Aug 03, 2025 |

## Conclusion 
This planning log captures our response to the urgent database issues encountered after the holiday period. By restoring the database using migration scripts and updating the environment configuration to use the Nectar database, we aim to quickly resolve the connectivity issues. The detailed steps and follow-up actions will ensure that we stabilize the system and are prepared for further improvements once the new survey data is provided by the client.
