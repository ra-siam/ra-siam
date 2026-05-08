# Hi, I'm Siam

Self-taught full-stack developer + IT graduate (Networking & Security), pivoting into software engineering through ambitious solo projects. Sydney, NSW (relocating to Hobart, TAS — June 2026).

I work across product, engineering, and DevOps end-to-end on personal projects, learning the modern web stack by building real things from scratch.

---

## Currently Building

**Deshi Drip** — a centralised streetwear marketplace concept for Bangladesh. Aiming to be the *Culture Kings of BD*. My first major coding project, started October 2025. The first iteration collapsed under untested rapid feature work (2000+ errors after three weeks of feature-rushing without tests or build gates) — I made the call to discard and restart from scratch with discipline. The current build: 158-model Postgres schema across 18 domain files, custom multi-portal auth (4 user groups, per-portal JWT, WebAuthn, argon2id), modular monolith on pnpm + Turborepo with adapter patterns for storage / email / SMS / payments / courier. The architectural maturation is sequenced across multiple phases.

**feebaq** — a multi-tenant SaaS concept for ecommerce merchants. Demo store currently live. Multi-tenant Organization-root design, pluggable provider architecture, clean separation between merchant data and platform code.

**A third project** — an ecosystem play I'm prototyping privately. More when it's ready to share.

> All three are personal/portfolio work — not commercial revenue-generating businesses (yet).

---

## Tech Stack

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=for-the-badge&logo=prisma&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=for-the-badge&logo=supabase&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![Zod](https://img.shields.io/badge/Zod-3068B7?style=for-the-badge&logo=zod&logoColor=white)
![Vitest](https://img.shields.io/badge/Vitest-6E9F18?style=for-the-badge&logo=vitest&logoColor=white)
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=for-the-badge&logo=playwright&logoColor=white)
![pnpm](https://img.shields.io/badge/pnpm-F69220?style=for-the-badge&logo=pnpm&logoColor=white)
![Turborepo](https://img.shields.io/badge/Turborepo-EF4444?style=for-the-badge&logo=turborepo&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)
![Railway](https://img.shields.io/badge/Railway-0B0D0E?style=for-the-badge&logo=railway&logoColor=white)
![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=cloudflare&logoColor=white)

*Background from university (Networking & Security major):*

![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonwebservices&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Kali Linux](https://img.shields.io/badge/Kali_Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white)
![C#](https://img.shields.io/badge/C%23-512BD4?style=for-the-badge&logo=csharp&logoColor=white)
![Tableau](https://img.shields.io/badge/Tableau-E97627?style=for-the-badge&logo=tableau&logoColor=white)

I lean toward: modular monoliths over microservices, adapter patterns for anything pluggable, schema-first design, decimal arithmetic for money, strict typing with no escape hatches, and writing the architecture decision before writing the code.

---

## How I Work

- Opinionated about quality — earned the hard way. No corner-cutting, no skipping tests, no "we'll fix it post-launch." (My first iteration of Deshi Drip taught me this lesson by collapsing.)
- Heavy investment in `.context/` docs + decision logs — if a system is worth building, it's worth being legible 6 months later. [→ sample decision log](https://gist.github.com/ra-siam/6fee429973313c4b27a7b32298f5e417)
- Comfortable owning the entire pipeline: product spec → schema → backend → frontend → infra → deploy.

---

## How I Architect

A typical request through one of my platforms:

```mermaid
flowchart TD
    Client[Web · Mobile · Widget] --> Edge[Edge Layer<br/>auth · rate-limit · CSRF]
    Edge --> Routes[Route Layer<br/>typed handlers · Zod validation]
    Routes --> Services[Domain Services<br/>typed errors · transactions]
    Services --> Data[(Postgres<br/>+ Prisma)]
    Services --> Cache[(Redis<br/>cache · queue · sessions)]
    Services --> Storage[(Object Storage<br/>R2 / S3)]
    Services --> Workers[Background Workers<br/>BullMQ · scheduled jobs]
    Workers --> Data
    Workers --> Notify[Notifications<br/>Email · SMS]
    Services --> Notify
    Services --> Audit[(Audit Log<br/>pluggable sink)]
```

Common patterns across my work: typed error throws (services don't return error envelopes), strict module boundaries enforced at the dependency graph, adapter interfaces for any external provider (storage, email, SMS, payment gateway, courier), and a single primary database with serializable isolation for any financial operation.

---

## Where to Reach Me

- Email — [siamr4@gmail.com](mailto:siamr4@gmail.com)
- LinkedIn — [ra-siam](https://www.linkedin.com/in/ra-siam)
- GitHub — you're here

**Open to:** junior or entry-level software engineering / full-stack developer / web developer / IT roles in Australia (Sydney now, Hobart from June 2026 — on-site, hybrid, or remote). Graduate programs, internships, contract, or full-time. Also open to early technical co-founder conversations with the right partner.

Most of my code lives in private repos — happy to walk through architecture, decisions, and code in a 1:1 conversation.
