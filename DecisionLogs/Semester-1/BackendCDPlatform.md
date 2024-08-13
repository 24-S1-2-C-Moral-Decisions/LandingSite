# DECISION LOG 
## Decision Details 
- Date: 19/04/24 
- Decision Maker: Xinlong Wu
  
## Background 
To streamline our deployment process and maintain high availability of our backend services, we evaluated various platforms for hosting and automatic deployment. Given the team's budget constraints and the need for a reliable and cost-effective solution, we considered several options including AWS Web App services, setting up Jenkins on an AWS server, and using Azure WebApp services.

## Decision Options 

- Option 1: Utilize AWS Web App services, known for robustness but relatively expensive without any free tier available for students.
- Option 2: Create an AWS server and set up Jenkins for continuous deployment, offering more control but requiring more maintenance.
- Option 3: Use Azure WebApp services, which offers a $100 annual free credit but reported to be less user-friendly.


## Decision Rationale 

After careful consideration of the costs, benefits, and potential drawbacks of each option, the team decided to opt for Azure WebApp services. This decision was driven by several factors:

- Cost-Effectiveness: Azure’s $100 annual free credit presents a significant cost advantage, especially important given our limited budget.
- Community Support: Initial concerns about the user-friendliness of Azure WebApp services were mitigated by the active community support, which the team could leverage to resolve potential issues.
- Simplicity and Efficiency: While Azure may not be as straightforward as AWS in some respects, the integration of deployment tools and services it offers aligns well with our project needs without the overhead of managing our own Jenkins server.

## Decision Outcome 
The final decision was to proceed with Azure WebApp services for our backend’s automatic deployment. This platform not only meets our budgetary requirements but also supports our deployment needs adequately. Community resources and support were identified as valuable aids to overcome any usability challenges.

## Implementation Plan 

The implementation involves:

1. Setting up our backend services on Azure WebApp.
2. Configuring the continuous deployment pipeline within Azure to automate our deployment process.
3. Leveraging community forums and support for troubleshooting and optimizing our use of Azure WebApp.

## Conclusion 

Selecting Azure WebApp services for our backend’s automatic deployment aligns with our financial constraints and project requirements. By effectively using the available resources and community support, we can manage the platform’s complexities and ensure a smooth and cost-effective deployment process. This decision supports our goal of maintaining an efficient and robust backend infrastructure while staying within our budget.
