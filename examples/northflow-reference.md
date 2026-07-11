# Example: Northflow (T3 reference)  
  
Payment orchestration middleware, backend-to-backend, multi-tenant.  
  
## Yang membuatnya contoh T3 yang baik  
- AuthN: API-key per client, resolve ke principal (clientId, sourceApp, scopes).  
- AuthZ: 24 scope per route + grant ReBAC per (client, merchant); cross-merchant => 403.  
- Privileged: dashboard internal = client `kind: 'internal'` yang bypass grant secara sah (bukan shared token).  
- Arsitektur: domain -> use-case -> repository interface -> infrastructure (Drizzle adapter) -> route.  
- Dua lapis auth (rencana): better-auth untuk login ops user + API-key untuk service-to-service.  
  
Link repo: <isi URL repo Northflow Anda>
