# Devrehane — Electronics & Robotics E-Commerce Platform

Devrehane is a production full-stack platform that combines e-commerce and educational experiences for electronics, robotics and maker communities. It is a full-stack web application with a public storefront, an admin panel, product and category management, an order and return workflow, inventory logic, and transactional email — built with a strong focus on **server-side data integrity and security**.

🌐 **Live:** https://www.devrehane.net

> This is a public **portfolio / case-study overview**. The application source code is kept in a private repository for security and business reasons; no keys or production configuration are published here.

## Tech Stack

- **Frontend:** React, Vite, TypeScript, Tailwind CSS
-Backend / Data:
-PostgreSQL (Supabase-managed), SQL RPCs, Database Triggers, Row Level Security, Supabase Auth, Supabase Storage, Supabase Edge Functions, SQL migrations
- **Infrastructure / Tooling:** Vercel, Resend (transactional email), Git / GitHub
- ## Preview:
<img width="2048" height="908" alt="egitim setleri" src="https://github.com/user-attachments/assets/45deb684-fee0-4ee7-8dc3-ee9d9ee2dd09" />
<img width="2048" height="780" alt="adminpage" src="https://github.com/user-attachments/assets/ac37937a-31ed-4ee3-8cb2-56a41f8ddf88" />
<img width="2048" height="969" alt="akademi" src="https://github.com/user-attachments/assets/49c94a78-5827-4c85-8cd6-4fad7655df11" />

## Main Features

- Public e-commerce storefront (Turkish UI, SEO-friendly routing)
- Product and category management
- Admin panel with role-based access control
- Separate admin and public authentication sessions
- Shopping cart and checkout flow
- One-way order status workflow
- Inventory / stock logic
- Return request workflow (customer ↔ admin)
- Transactional email notifications with delivery tracking
- Password strength feedback and authentication UX hardening

## Security & Data-Integrity Architecture

Security is treated as a first-class, database-level concern rather than something enforced only in the frontend:

- **Server-authoritative pricing & totals** — order subtotals, shipping and totals are computed and enforced inside the database. The client submits only product references and quantities; prices and totals cannot be manipulated from the client.
- **Atomic, idempotent order & payment transitions** — stock deduction at payment runs as a single atomic transaction with deterministic, deadlock-safe locking and idempotency guarantees, so retries or double submissions cannot double-deduct inventory or duplicate customer emails.
- **Defense in depth** — access control combines Row Level Security, privileged (`SECURITY DEFINER`) database functions as the controlled write path for sensitive operations, database triggers that enforce invariants, and CHECK constraints as a final safety net even if the API layer is bypassed.
- **Privilege hardening** — role-sensitive fields are protected against client-side modification at the database level.
- **Separated trust boundaries** — outward-facing operations (signature verification, outbound HTTP, transactional email) are isolated in Edge Functions; database functions never make external calls while holding locks.
- **Email quota guard** — a multi-layer guard prevents uncontrolled automated transactional email usage.
- **Verified, not assumed** — security-critical changes are validated with production smoke tests and adversarial tests (e.g. confirming unauthenticated or unauthorized calls are rejected).
- **Operational hygiene** — admin/public session isolation, production security headers, and authentication messages designed to avoid user enumeration.

## Recent Production Work

- Migrated order creation and payment to server-side database RPCs (server-computed totals, atomic and idempotent stock handling).
- Hardened the admin order workflow with strict one-way status transitions and confirmation prompts before customer-facing actions.
- Extended the transactional email system for order and return events, with database-backed send tracking and a sending quota guard.
- Replaced broad client-side order updates with secure RPC-based return handling.
- Strengthened authentication: separated admin/public sessions, password policy and strength feedback, anti-enumeration messages.
- Stabilized production deployment and routing (SPA rewrites, asset paths for deep routes, security headers).

## Development Workflow

Developed with Git-based version control and reviewed before each deployment. AI-assisted tools (ChatGPT, Claude, Gemini) are used for code analysis, debugging, documentation and research support; final architecture decisions, integration and testing are reviewed and validated manually.

## Roadmap (planned, not yet in production)

- **IoT interfaces** — real-time data visualization for sensor-based robotics prototypes.
- **AI-assisted subtractive inventory** — users enter components they already own; the system compares them against a target project's bill of materials (BOM), identifies missing parts, and generates an optimized shopping list/cart.
- **Project-based shopping** — pick a target build (e.g. an Arduino robot or sensor prototype); the platform computes what is already available vs. what still needs to be purchased.
- **Cross-domain scalability** — the same "target requirements − available resources = optimized list" logic generalizes beyond electronics (recipes, DIY projects, learning kits).
- **Sustainable architecture** — built to extend, not as a throwaway prototype.

## Source Code

The main application lives in a private repository. This public repository serves as a portfolio overview and case study for the Devrehane project.
