# Block: Acceptance Criteria (make results measurable, not vibes)  
  
- Type-check clean across all packages.  
- All tests pass, 0 failures.  
- (T1+) wrong role/scope => 403; (T2/T3) cross-tenant access => 403.  
- Migrations run clean on a fresh DB; no unexpected schema diff.  
- No new `any` / `@ts-ignore`.  
- Build succeeds; (T0) no console errors, mobile-friendly, Lighthouse > 90.
