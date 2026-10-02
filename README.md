# Daniel Watson

I build software that runs real businesses: work-order systems, lead pipelines, and AI agents for the trades and clinics. 20 years in sales and construction before this, so most of what's here started because a real operation needed it and nothing off the shelf fit.

I build with AI coding agents and own the product decisions: what to build, what to cut, how it's priced, and whether it actually works in production. Top 1% of Replit Agent users, Replit Level 3 certified.

**Looking for:** product, GTM engineering, or forward-deployed roles where building the thing and talking to customers are the same job.

**Working in:** TypeScript · Next.js · React · Python (FastAPI) · Postgres / Supabase · Node · Tailwind
**Building with:** Claude API · OpenAI · ElevenLabs · Whisper · Telnyx / Twilio · Google Places · Stripe · Vercel · Playwright

---

## Selected work

**[just-grit](link)**: Local business lead engine
FastAPI service that pulls businesses from Google Places, scores their websites on concrete criteria, and generates specific talking points for a sales call. Outreach is built only from what it finds, so nothing gets invented. Live at justgrit.thewatsonfactor.dev/welcome.

**[novara-lead-scraper](link)**: Lead sourcing pipeline
Google Places → Hunter enrichment → Claude fit-scoring → outreach queue. Built for a construction firm that was doing this by hand.

**[kitt-voice-agent](link)**: Voice-first AI chief of staff
A push-to-talk AI agent that runs my day and supervises two businesses on its own. Mac Studio host with a secure phone console.
- **Three-tier routing to control cost:** built-in commands (free, instant) → local Qwen 2.5 7B via Ollama (free, under 3s) → Claude with 12 tools for anything involving data or action (~2¢, 4–9s). Hard $5/day spend cap.
- **Real actions, with guardrails:** places phone calls through Telnyx (message calls with press-1 confirm or recorded reply, or live connect), reads and sends email, and manages to-dos. Nothing dials or sends without a spoken yes; contacts only, daily call limits, and quiet hours.
- **Autonomous business operator:** checks both businesses every 15 minutes, refills outreach, retries failed posts, pauses cold email if deliverability drops, texts back inbound leads, and only escalates hot leads and breakages. Spoken briefing every morning.
- **Learns from use:** saves standing instructions, logs corrections, routes topics to Claude after the local model misses twice in a week, and runs a weekly self-review that sets the build list.
Stack: Node/TypeScript · Whisper · Ollama · Claude API · Telnyx · SQLite · Cloudflare Tunnel + Access

**[watson-maintain](link)**: Multi-tenant facility maintenance platform (built for a partner's business)
Next.js 15 + Supabase with row-level security for tenant isolation, a full work-order lifecycle, and AI-assisted triage. Separate route groups per role (requester / tech / manager). Accessibility built in.

**[elecpro](link)**: Electrical contractor job management
TypeScript API with JWT auth, Postgres, and Claude-assisted estimates generated from job notes.

## Not public (client and production systems)

**Watson Practice OS**: AI practice management platform running at a multi-location clinic group. It replaces separate phone, scheduling, charting, billing, and records systems: a bilingual AI receptionist, personal injury billing, and a records vault with legal hold and audit logs. 430+ API endpoints and 5,000+ automated tests, with a second AI agent that must reproduce each result before code merges.

**HomeRepair.tech**: Field-service platform running a real home-services business. TypeScript monorepo across API, web, and three mobile apps, with Postgres, Stripe memberships, AI voice intake, and Playwright end-to-end coverage.
