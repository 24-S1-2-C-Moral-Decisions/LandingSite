# DECISION LOG 
## Decision Details 
- Date: Mar 16
- Decision Maker: All members
  
## Background 
As the team embarked on developing four distinct surveys utilizing a shared template repository, the necessity for a streamlined and efficient workflow became apparent. The primary goal was to ensure that each survey could be developed concurrently without interference, while also maintaining the ability to track progress comprehensively through Jira. Additionally, the integration of Continuous Integration (CI) processes for quality assurance and the requirement for rigorous review protocols were identified as critical components to uphold the project's integrity and alignment with organizational standards.

## Decision Options 

[List the different options or alternatives that were considered when making the decision.] 

- Option 1: Develop all surveys within a single repository, using branches for each survey.
- Option 2: Use separate repositories for each survey, created by forking the template repository.
- Option 3: Use a monorepo approach, where each survey is a module within the repository but separated logically.


## Decision Rationale 
After thorough consideration, including a review of the existing infrastructure, project requirements, and potential scalability, Option 2 was selected. This decision was influenced by several factors:

- Isolation of Development Work: Forking the repository for each survey ensures that work is isolated, minimizing the risk of conflicts and facilitating focused development efforts.
- Project Tracking: Separating surveys into different repositories simplifies the process of tracking progress and managing tasks in Jira, allowing for clearer visibility and accountability.
- Quality Assurance: Leveraging CI processes in each repository ensures that any updates or changes undergo rigorous testing, maintaining the high quality of the surveys.
- Review Process: Enforcing a requirement for at least three reviewers to approve pull requests before merging aligns with the team's commitment to quality and collaborative review, ensuring that all contributions are scrutinized for excellence.

## Decision Outcome 
The final decision was to proceed with Option 2, forking the template repository for the development of each individual survey. This approach was selected for its ability to provide a clear and efficient development workflow, enhance project tracking capabilities, and uphold the quality standards of the project through robust review and testing processes.

## Implementation Plan 

The implementation plan involves the following steps:

- Fork the template repository for each of the four surveys.
- Assign development teams to each survey repository.
- Integrate CI processes in each repository to enforce code quality and testing standards.
- Monitor progress through Jira, with tasks and milestones clearly defined for each survey.
- Upon completion, submit pull requests from each forked repository to the main repository for review.
- Require a minimum of three approvers for each pull request before merging.

## Risks and Mitigation 

- Risk: Potential delays in review processes due to the requirement for three approvals.
  - Mitigation: Allocate dedicated reviewers for each survey and establish clear timelines for review processes.

- Risk: Integration challenges when merging surveys back into the main repository.
  - Mitigation: Conduct preliminary integration tests in forked repositories and ensure thorough review of pull requests to identify and resolve conflicts early.

## Follow-up Actions 

- Schedule regular progress reviews to ensure milestones are met according to the project timeline.
- Prepare documentation and guidelines for the development and review process to ensure consistency and clarity.

## Conclusion 

The decision to utilize separate repositories for the development of each survey through forking the template repository represents a strategic approach to managing this complex project. By ensuring isolation of development efforts, facilitating efficient progress tracking, and enforcing strict quality control measures, this decision is poised to significantly contribute to the successful execution and high-quality outcomes of the survey development project.