# DECISION LOG 
## Decision Details 
- Date: 16/09/2024
- Decision Maker: all the team member and client
  
## Background 
As the number of pages continues to grow, we've realized that the original setPage method is no longer sufficient to meet our needs. Therefore, we plan to implement routing to handle page navigation. 

## Decision Options 

- [Option 1] We will use the routing API provided by Next.js to help us implement page navigation.

## Decision Rationale 

The implementation of page navigation has become more flexible and easier to maintain.


## Decision Outcome 

We decided to implement the Option 1 that we will use the routing API provided by Next.js to help us implement page navigation as this API is powerful and easy to management.

## Implementation Plan 
- Timeline: Completed by 18 September 2024
- Responsible Parties: Front end develop team
- 
## Risks and Mitigation 

-Risk： Using the routing components provided by Next.js may lead to some compatibility issues.
  -Mitigation: Through testing to make sure the front end can run successfully. 
## Follow-up Actions 

- Update all document to reflect the implementation of route.
- Schedule a review session in one month to assess the impact of these changes on system performance and user experience.

## Conclusion 

After implementing routing, navigation between pages becomes more flexible. 
There's no need to use the setPage method to handle routing, which makes the code easier to maintain and improves the overall user experience.
