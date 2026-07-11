# T0 — Static / Content Site  
  
Contoh: landing page, company profile, portofolio.  
  
## Blok aktif  
- ON: Block 0 (Project & Goals), Block 1 (Tech Stack), Block 7 (Quality subset), Block 10 (Acceptance subset)  
- OFF: Block 2-6 (arch/auth/authz/tenant), Block 8-9 (anti-patterns backend, testing backend)  
  
## Struktur  
- Component-based, konten di MDX/CMS, tidak ada backend logic.  
  
## Tech stack (contoh)  
- Next.js / Astro + Tailwind, deploy ke Vercel/Netlify.  
  
## Acceptance criteria  
- Responsive, accessible (ARIA), SEO meta lengkap.  
- Lighthouse > 90, no console errors, mobile-friendly.  
- Build sukses.
