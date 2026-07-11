# Block: Data Layer conventions  
  
- Every repository is an interface; the DB implementation is a separate adapter.  
- List endpoints return a consistent envelope:  
  `{ entries, total, limit, offset }`.  
- Pagination: sane default (e.g. 50) and hard max (e.g. 200).  
- Migrations are additive and numbered sequentially; never edit an applied one.  
- A fresh DB must migrate clean; `generate` must show no unexpected diff.  
- No raw SQL in route handlers; queries live in the repository adapter.
