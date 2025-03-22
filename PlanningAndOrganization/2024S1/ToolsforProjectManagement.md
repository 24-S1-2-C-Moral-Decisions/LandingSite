# DECISION LOG 
## Decision Details 
- Date: Mar 8th, 2024
- Decision Maker: All members
  
## Background 
As the project begins, we need to start our own work and need to decide on the technology stack and tools to use

## Challenges Revisited

- Currently the project uses python and the potly framework. It has some advantages in data processing, but it is limited in page display and rendering.
- Need to harmonize the technology stack as much as possible to keep the project streamlined
- Effective project management to make it simpler for developers and clients to start projects

## Decision Rationale 
**Tooling for Development:**
1. Version Control System: Git remains the cornerstone for version control due to its widespread adoption and compatibility with existing tools.
2. Development Environment: We use servers as well as Docker to unify the development environment so that every developer can get started straight away.
3. Testing Tools: Postman will continue to be the primary tool for testing API endpoints due to its ease of use and comprehensive testing capabilities.
4. Repo Structer: Integrate the front-end code repository and back-end code repository in a submodule fashion to maintain uniformity while separating front-end and back-end development, so that projects can be deployed with a single click.

## Decision Outcome 
To ensure that the project runs efficiently and smoothly, this text outlines the various development tools and processes we will employ. Git is the foundation of our version control, managing code changes efficiently thanks to its wide adoption and compatibility with existing tools. In order to get every developer up to speed, the development environment will be uniformly configured with a combination of servers and Docker to provide a consistent development experience. For API endpoint testing, we will continue to use Postman as our primary tool because of its ease of use and comprehensive testing capabilities. Finally, for the code repository, we'll use submodules to unify the front-end and back-end code. This approach maintains overall consistency, separates front-end and back-end development, and supports one-click deployment of projects. In short, by using these tools and processes, we can guarantee code stability, improve development efficiency, and simplify the deployment process of the project.