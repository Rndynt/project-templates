# T3 — Multi-Tenant Platform  
  
Contoh: Northflow, marketplace, platform B2B.  
Model akses: ReBAC/ACL per-(client, tenant) + isolasi tenant + fail-closed.  
  
## Blok aktif (SEMUA)  
- ON: Block 0-10 penuh.  
- AuthN: API-key (`blocks/auth-api-key.md`) untuk backend-to-backend;  
  opsional better-auth (`blocks/auth-better-auth.md`) untuk login ops user (dua lapis, jangan dicampur).  
- AuthZ: `blocks/authz-scope-rebac.md` (scope per route + grant per (client, tenant)).  
- Block 5: privileged/internal client WAJIB atribut eksplisit (`kind: 'internal'`), bukan bypass implisit.  
  
## Acceptance criteria  
- Cross-tenant access => 403; request tanpa scope => denied.  
- Privileged hanya via atribut eksplisit, tidak ada shared/global token.  
- Migrations clean di DB baru; type-check clean; tests 0 fail.  
  
Lihat contoh nyata: `examples/northflow-reference.md`.
