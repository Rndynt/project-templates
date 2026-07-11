# Block: AuthZ — Scope + ReBAC/ACL (multi-tenant)  
  
- Scope-based authorization per route (OAuth2-style). Missing scope => SCOPE_DENIED.  
- ReBAC/ACL grant per pasangan (client, tenant). No grant => MERCHANT/TENANT_ACCESS_DENIED.  
- SourceApp enforcement: sourceApp di body harus cocok credential; mismatch => ditolak.  
- Fail-closed / deny-by-default di semua titik. Least privilege.  
- Privileged/internal client = atribut eksplisit (kind: 'internal'), bukan bypass implisit.
