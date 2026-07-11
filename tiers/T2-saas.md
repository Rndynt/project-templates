# T2 — Multi-User SaaS  
  
Contoh: app dengan banyak user/organisasi, data milik masing-masing user/org.  
Model akses: RBAC + row-level ownership (setiap record punya owner/org).  
  
## Blok aktif  
- ON: Block 0, 1, 2 (clean-arch penuh), Block 3 (better-auth), Block 4 (RBAC + ownership check), Block 7, 8, 9, 10  
- OFF/opsional: Block 5 (privileged internal), ReBAC penuh (pakai ownership dulu)  
  
## Auth  
- `blocks/auth-better-auth.md` + plugin organization jika perlu.  
- AuthZ: RBAC + setiap query difilter `WHERE owner_id = session.userId` (atau org_id).  
  
## Acceptance criteria  
- User A tidak bisa akses data user B => 403/404.  
- Type-check clean, tests 0 fail (termasuk test ownership negatif).
