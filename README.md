## Daniel Watson

I build software that runs actual businesses — work-order systems, lead pipelines, and AI agents for the trades. Self-taught, shipping-first: most of what's here started because a real operation needed it and no off-the-shelf tool fit.

Currently looking for a full-stack or AI engineering role.

**Working in:** TypeScript · Next.js 15 · React · Python (FastAPI) · Postgres / Supabase · Node · Tailwind  
**Building with:** Claude API · ElevenLabs · Whisper · Google Places · Vercel · Playwright

---

### Selected work

**[watson-maintain](https://github.com/thewatsonfactor-dot/watson-maintain)** — Multi-tenant facility maintenance platform  
Next.js 15 + Supabase with row-level security enforcing tenant isolation at the database layer, full work-order lifecycle, and AI-assisted triage. Separate route groups per persona (requester / tech / manager). Accessibility built in — 44px touch targets, reduced-motion support, explicit AI disclosure.

**[kitt-voice-agent](https://github.com/thewatsonfactor-dot/kitt-voice-agent)** — Voice-first personal AI agent  
Wake-word detection (Picovoice) → local Whisper sidecar for STT → Claude for reasoning with an Ollama fallback → ElevenLabs for speech. Runs offline-capable on-device where it can; degrades gracefully when it can't.

**[just-grit](https://github.com/thewatsonfactor-dot/just-grit)** — Local business site scoring engine  
FastAPI service that pulls businesses from Google Places, scrapes and scores their websites on concrete criteria, and generates the specific talking points for a sales call. Python, async, rate-limit aware.

**[novara-lead-scraper](https://github.com/thewatsonfactor-dot/novara-lead-scraper)** — Lead sourcing pipeline  
Google Places → Hunter enrichment → Claude fit-scoring → outreach queue. Built for a construction firm that was doing this by hand.

**[elecpro](https://github.com/thewatsonfactor-dot/elecpro)** — Electrical contractor job management  
TypeScript API with JWT auth, Postgres, and Claude-assisted estimate generation from job notes.

**Not public:** my largest system is a field-service platform running a real home-services operation — TypeScript monorepo across API, web, and mobile, with Postgres, payments, AI voice intake, and Playwright end-to-end coverage. It's private because the business is a live asset. Happy to walk through the architecture and trade-offs in an interview.

---

### How I work

I start from the operational problem, not the stack. Most of these projects exist because someone was doing something in a spreadsheet or on paper, and the interesting engineering was in the constraints — multi-tenancy that can't leak, voice latency budgets, API rate limits, people who will stop using the tool if it takes more than three taps.

I'm self-taught and comfortable saying so. I read source, I write tests for the parts that would actually hurt, and I'd rather ship something small that works than architect something large that doesn't.

**Site:** [thewatsonfactor.dev](https://thewatsonfactor.dev) · **LinkedIn:** [daniel-watson](https://www.linkedin.com/in/daniel-watson-2b38776)
