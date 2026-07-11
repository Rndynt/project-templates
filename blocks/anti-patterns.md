# Block: Forbidden Anti-Patterns  
  
- No shared/global auth token.  
- No implicit privilege bypass (privileged harus atribut eksplisit).  
- No DB calls di route handlers.  
- No business logic di HTTP/UI layer.  
- No `any` untuk membungkam type-checker.  
- No breaking multi-tenant isolation demi kemudahan.
