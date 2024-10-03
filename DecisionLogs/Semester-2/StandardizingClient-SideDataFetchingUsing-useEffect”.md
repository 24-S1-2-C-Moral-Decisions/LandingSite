# DECISION LOG 

## Decision Details 
- Date: October 1th, 2024
- Decision Maker: All members

## Background 
Previously, our webpage was fetching some data on the server side and some on the client side, which caused inconsistencies and challenges in setting up axios prefixes. The team identified the need for a more uniform approach to data fetching to simplify this process.

## Decision Options 
- **Option 1:** Continue with the current setup, where some data is fetched server-side and some client-side.
- **Option 2:** Standardize data fetching in the client side using `useEffect`, allowing easier configuration of axios prefixes and maintaining consistency across the app.

## Decision Rationale 
The team decided to shift all data fetching to the client side using `useEffect`. This approach simplifies axios prefix configuration, ensuring consistent and easily manageable data fetching across the app. It also provides flexibility for future enhancements while reducing potential complexities between server and client-side fetching.

## Decision Outcome 
The team opted for **Option 2**, moving all data fetching to the client side using `useEffect`. This decision ensures a more consistent development workflow and simplifies the handling of axios prefixes across different components.

## Implementation Plan 
1. Refactor all data fetching code to use `useEffect` on the client side.
2. Adjust axios configurations to set up appropriate prefixes for client-side requests.
3. Test the refactored code across different components to ensure functionality is intact and no issues arise from the change.

## Risks and Mitigation 
- **Risk:** Increased load on the client side could potentially impact performance.
  - **Mitigation:** Optimize data fetching by minimizing unnecessary API calls and improving caching mechanisms.

## Follow-up Actions 
1. Assign team members to refactor data fetching to the client side using `useEffect`.
2. Test and review the changes to ensure smooth data fetching and integration across components.
3. Monitor performance after the change and make adjustments if necessary.

## Conclusion 
This decision ensures consistency in data fetching, simplifies axios configuration, and improves maintainability. By using `useEffect` for client-side data fetching, the team enhances development efficiency and reduces the complexity of managing server-side logic.

