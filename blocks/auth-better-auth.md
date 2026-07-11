# Block: AuthN — better-auth (session-based)  
  
- Pakai better-auth untuk autentikasi (email/password + OAuth mis. Google).  
- JANGAN reimplement session, hashing, atau OAuth — gunakan built-in better-auth.  
- Route handler hanya membaca session user, lalu delegasi ke service layer.  
- Session cookie httpOnly; manfaatkan email verification & login rate limit bawaan.  
  
Contoh instruksi ke agent:  
> "Use better-auth (session, email/password + Google OAuth). Do NOT reimplement  
>  session/hashing/OAuth. Authorization is a separate layer (see authz block).  
>  No DB calls or business logic in the UI/route layer."
