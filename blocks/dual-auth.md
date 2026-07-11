# Block: Dual Authentication (human login + service-to-service)  
  
Use when ONE system is called by BOTH human operators (via a UI) AND  
other backends/services. Keep the two auth paths separate — never mix.  
  
## Two independent layers  
1. Human/user auth (the UI): better-auth session (email/password, OAuth).  
   - Identifies a PERSON (userId, role).  
   - Used by the internal dashboard / ops console.  
2. Service/machine auth (API): API-key credential.  
   - Identifies an APP/CLIENT (clientId, sourceApp, scopes).  
   - Used for backend-to-backend calls.  
  
## Rules  
- Do NOT authenticate services with a human session, and do NOT  
  authenticate a UI with a shared/global API token.  
- The UI backend (e.g. Next.js route/proxy) authenticates the human via  
  better-auth, THEN calls the API using its own per-client API credential.  
- Authorization stays explicit on both sides: RBAC for the human role,  
  scope + (ReBAC/internal) for the API client.  
- Privileged/internal service access is an EXPLICIT client attribute  
  (e.g. kind: 'internal'), never an implicit bypass.  
  
## Applies to  
- Northflow: better-auth for ops-user login on the dashboard +  
  per-client `nf.*` API credential (kind: 'internal') for the  
  dashboard-to-service calls.
