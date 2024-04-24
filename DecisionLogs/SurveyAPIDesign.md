# DECISION LOG 
## Decision Details 
- Date: 17/04/2024
- Decision Maker: All Members
  
## Background 
To support the client's survey distribution and data collection process, we needed to define APIs that would facilitate the flow of receiving survey participants via specific URLs and capturing their responses effectively. The client's workflow starts with users accessing a survey link with embedded parameters, which necessitates a dynamic API design that can cater to varying study requirements and ensure efficient data handling for compensation purposes.

## Decision Options 

- Option 1: Develop a single API that handles both sending survey questions and receiving responses but uses different endpoints for each task.
- Option 2: Create two separate APIs, one dedicated to sending survey questions based on studyId and another for receiving user responses along with profilicId.


## Decision Rationale 

The decision to go with Option 2 and create two separate APIs was based on the following considerations:

- Clarity and Separation of Concerns: Having separate APIs for sending questions and receiving answers enhances clarity in the API's structure and simplifies maintenance. Each API can be optimized for its specific task without complicating the logic.
- Scalability: Separate APIs allow for easier scaling of each service as the system grows. Changes and updates can be managed more efficiently, reducing the risk of affecting other functionalities.
- Security and Data Integrity: By separating the APIs, it becomes easier to implement specific security measures tailored to the data handling requirements of each API, particularly in terms of protecting participant identities and responses.


## Decision Outcome 

We defined two APIs to support the survey process:

- Survey Question API: This API accepts a studyId parameter and is responsible for generating and sending the appropriate survey questions to the user. It ensures that each participant receives the correct survey tailored to the study they are participating in.
- Survey Response API: This API receives the user's completed survey answers along with their profilicId. This data is crucial not only for the analysis and study outcomes but also to facilitate the client's process of compensating participants based on their unique profilicId.

## Conclusion 

By defining two distinct APIs for the survey process, we have created a robust framework that not only meets the client's requirements for efficient and secure data handling but also provides a scalable and clear structure for future enhancements. This decision aligns with our goals of providing high-quality, reliable service and maintaining the integrity and security of participant data.
