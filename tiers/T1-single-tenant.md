# T1 — Single-Tenant App  
  
Contoh: web management internal, online shop pribadi.  
Model akses: 1 owner + beberapa role user (RBAC). TIDAK perlu multi-tenant/ReBAC.  
  
## Blok aktif  
- ON: Block 0, 1, 2 (clean-arch ringan), Block 3 (AuthN via better-auth), Block 4 (AuthZ = RBAC), Block 7, 8, 9, 10  
- OFF: Block 5 (privileged internal client), multi-tenant + ReBAC di Block 4  
  
## Auth  
- Pakai `blocks/auth-better-auth.md` (session-based).  
- Pakai `blocks/authz-rbac.md` (role: admin/staff/customer).  
  
## Acceptance criteria  
- Unauth => redirect login; wrong role => 403.  
- Business logic terpisah dari UI; no `any`.  
- Type-check clean, tests 0 fail.
