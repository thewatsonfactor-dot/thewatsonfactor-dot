# Daniel Watson

I build software that runs real businesses: work-order systems, lead pipelines, and AI agents for the trades and clinics. 20 years in sales and construction before this, so most of what's here started because a real operation needed it and nothing off the shelf fit.

I build with AI coding agents and own the product decisions: what to build, what to cut, how it's priced, and whether it actually works in production. Top 1% of Replit Agent users, Replit Level 3 certified.

**Looking for:** product, GTM engineering, or forward-deployed roles where building the thing and talking to customers are the same job.

**Working in:** TypeScript · Next.js · React · Python (FastAPI) · Postgres / Supabase · Node · Tailwind
**Building with:** Claude API · OpenAI · ElevenLabs · Whisper · Telnyx / Twilio · Google Places · Stripe · Vercel · Playwright

---

## Selected work

**[just-grit](https://github.com/thewatsonfactor-dot/just-grit)**: The sales engine I run two businesses on.
Finds local businesses on Google Places, reads their websites, drafts outreach in my voice from what it found, sends inside safe hours, reads the replies, and tracks every deal through to a signed proposal. Nothing sends without my approval unless I turn on autopilot, and one "stop" reply ends the sequence everywhere.
Python (FastAPI) + SQLite · ~23,000 lines · 210 routes · 72 test files · in daily production · [live demo](https://justgrit.thewatsonfactor.dev/welcome)

## Just Grit, in detail

### What it does
- **Finds leads** by trade and town, with a hard monthly cap on paid Google requests so the bill can't run away. When the home towns run out, it widens to nearby towns on its own.
- **Writes and sends outreach.** It learns my voice from my sent mail, drafts only from what it found on each business, throws out drafts that read like a bot, and sends inside the hours each audience actually reads email.
- **Reads replies** and sorts them: bounce, auto-reply, out of office, "stop," or a real person. Real people go straight to the top of my call list.
- **Runs the deal:** stages, contacts, deals priced from a product catalog, follow-up dates on a calendar, and bids and proposals attached to each account.
- **Handles the phone:** click-to-call, missed-call text-back, and Telnyx webhooks for AI receptionists, with an alert to my phone when a call comes in.
- **Manages reputation:** posts to Facebook and Instagram, writes captions from the photo, and watches my Google reviews and my competitors.

### Decisions I can talk through
- **One database file per business, not a `workspace` column.** A column means a `WHERE` clause on hundreds of queries, and the first one I forgot would silently mix two businesses' leads. Separate files make that bug impossible to write.
- **Approval first.** Autopilot is opt-in, and even then it obeys sending windows, hourly and daily caps, and a 48-hour no-repeat rule.
- **One suppression list everything reads.** A single "stop" removes that domain from the sender, the lead finder, and the site analyzer at once.
- **Built to fail visibly.** Plain-English errors, nightly backups kept 30 days, a watchdog that texts me if the app goes down, and a release script that rolls itself back when tests fail.
- **Secrets stay out of the code.** Keys live in the database, and the API only ever reports whether a key exists, never its value.

**Stack:** Python · FastAPI · SQLite · vanilla JavaScript (no build step) · Telnyx · Google Places · IMAP/SMTP · Cloudflare Tunnel + Access
Full write-up in the [just-grit README](https://github.com/thewatsonfactor-dot/just-grit).

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
