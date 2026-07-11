# Block: AuthZ — RBAC (role-based)  
  
- Role tetap: mis. admin / staff / customer.  
- Setiap route/aksi butuh role minimum; mismatch => 403.  
- Untuk T2: tambahkan ownership check (record difilter per owner/org).  
- Fail-closed / deny-by-default. Least privilege.
