# Block: Architecture (Clean / Hexagonal)  
  
- Layers: domain (entities, value objects) → application (use-cases) →  
  infrastructure (repository implementations, external adapters) →  
  interface (HTTP routes / controllers).  
- Rule: route handlers NEVER call the DB directly. They validate input,  
  enforce auth, call a use-case, then serialize the output.  
- Repositories are interfaces defined in the domain/application layer;  
  concrete DB adapters live in infrastructure (Ports & Adapters).  
- Dependency injection via a single composition root / container.  
- Business logic lives ONLY in use-cases, never in routes or UI.
