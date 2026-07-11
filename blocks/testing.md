# Block: Testing  
  
- Every access-control rule has a test, including NEGATIVE cases  
  (cross-tenant => 403, missing scope => denied, wrong role => 403).  
- Unit tests for use-cases; integration tests for routes + auth.  
- (If API) OpenAPI/route parity test so docs never drift from routes.  
- Tests must be deterministic and run on a clean DB.
