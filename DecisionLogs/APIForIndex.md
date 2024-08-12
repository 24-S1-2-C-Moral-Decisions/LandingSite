# DECISION LOG 
## Decision Details 
- Date: Aug 7th, 2024
- Decision Maker: All members
  
## Background 
The development team is tasked with designing the backend API that the Index page will call. We currently have a backend developed for the Survey application and initially planned to integrate the new API requirements into this existing setup. However, an alternative proposal was made by a team member, Ceming, who suggested leveraging the Next.js framework's capability to directly access the database, potentially simplifying the architecture by eliminating the need for a separate backend service.

## Decision Options 
- Option 1: Extend the existing Survey backend to handle the new API requirements for the Index page.
- Option 2: Utilize Next.js's direct database access feature to handle data retrieval and management from the Index page, avoiding the need for additional backend development.

## Decision Rationale 
Considering the innovative approach proposed by Ceming, which could significantly streamline development and reduce complexity, it was agreed that a demonstration would be the best way to evaluate this option's feasibility. This decision was influenced by:
 1. If successful, using Next.js to directly access the database could simplify our technology stack and reduce the workload on backend services.
 2. Given that other team members are not familiar with this functionality of Next.js, proceeding directly with implementation carries risks of delays or issues if the team cannot adequately support the technology.
 3. Allowing Ceming to create a demo provides a low-risk method to assess the practicality and effectiveness of this approach without committing significant resources.

## Decision Outcome 
The team decided to temporarily hold off on finalizing the API design decision until Ceming can develop and present a functional demo. This demonstration will help determine if Next.js’s direct database access can meet our needs for the Index page effectively and securely.

## Implementation Plan
 1. Ceming will develop a demo using Next.js to directly interact with the database, aimed at fulfilling the requirements of the Index page.
 2. The demo will be reviewed in a subsequent team meeting, where its functionality, performance, and security will be evaluated.
 3. Based on the outcome of the demo presentation, the team will decide whether to adopt this approach or proceed with extending the existing backend.

## Follow-up Actions
 1. Schedule a presentation for Ceming to showcase the demo.
 2. Prepare a contingency plan in case the demo does not meet the project’s requirements or introduces significant risks.
 3. Organize training for the team on Next.js’s database access features if the demo is successful and the approach is adopted.

## Conclusion
This decision to explore an innovative approach through a practical demonstration reflects the team’s commitment to efficient and effective solutions while managing risks associated with new technology adoption. This process will ensure that the team is well-informed and confident in whichever API design approach is ultimately chosen.

