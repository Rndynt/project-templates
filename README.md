# Project Templates  
  
Reference templates untuk membangun project baru bersama AI agent.  
Alur pakai:  
1. Jelaskan bisnis Anda ke agent.  
2. Beri agent link repo ini.  
3. Agent memilih TIER dari matrix di bawah, lalu menarik blok yang relevan dari `blocks/`.  
  
## Tier Selector  
  
| Tier | Contoh | Model akses | Arsitektur | Auth |  
|------|--------|-------------|------------|------|  
| T0 | Landing page, company profile | Tidak ada / admin CMS | Component-based, no backend | — |  
| T1 | Admin internal, online shop pribadi | 1 owner + role (RBAC) | Clean-arch ringan | better-auth (session) |  
| T2 | Multi-user SaaS | RBAC + row-level ownership | Clean-arch penuh | better-auth (session) |  
| T3 | Platform multi-tenant (mis. Northflow) | ReBAC/ACL + isolasi tenant | Clean/hexagonal penuh | API-key + (opsional) better-auth |  
  
Aturan: jangan pakai ReBAC/per-tenant grant (T3) untuk kebutuhan T1.  
Skalakan sesuai jumlah tenant dan sensitivitas data, bukan sekadar "besar/kecil".  
  
## Cara memilih blok  
- Tiap file `tiers/*.md` menyebut blok mana ON/OFF.  
- Detail blok ditulis sekali di `blocks/`, di-referensikan oleh tier.  
- Contoh nyata T3 ada di `examples/northflow-reference.md`.
