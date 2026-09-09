# Services & Upwork Project Catalog

Two things here: the **services you can honestly sell** (with pricing), and the
**Project Catalog listings** — Upwork's fixed-price storefront. Catalog projects
matter more than usual for you: clients browse and buy them directly, so they
generate work without you spending Connects on proposals.

---

## What you can sell — with pricing

Rates assume ~$18–20/hr effective, worked back into fixed prices. Always quote
fixed price for defined work.

| # | Service | Evidence you can point at | Fixed price | Timeline |
|---|---------|---------------------------|-------------|----------|
| 1 | **Business admin dashboard / internal tool** — roles, permissions, data entry, reports | Petrol station system | $700–2,500 | 2–5 weeks |
| 2 | **Next.js + Supabase web app** — auth, database, server actions | Meridian, Wild Oasis | $500–2,000 | 2–4 weeks |
| 3 | **Marketing site / landing page** — fast, responsive, animated | Core Stack, Roaster, Meridian | $250–800 | 4–10 days |
| 4 | **Figma / design → pixel-accurate Next.js build** | Core Stack (45 pages), Roaster | $200–1,200 | 3 days–3 weeks |
| 5 | **Supabase setup: schema, RLS, auth** — standalone engagement | Pump system RLS + triggers | $300–900 | 1–2 weeks |
| 6 | **Multi-step form / lead funnel + admin panel** | Meridian intake funnel | $350–900 | 1–2 weeks |
| 7 | **React Native (Expo) Android app** | The Ledger | $600–2,000 | 2–5 weeks |
| 8 | **Next.js web app → offline Windows desktop (Electron)** | PSX RSI app | $400–1,200 | 1–3 weeks |
| 9 | **AI feature integration** — chat, assistants, AI-assisted forms | Meridian (Vercel AI SDK) | $300–1,000 | 1–2 weeks |
| 10 | **Bug fixing / rescue on an existing Next.js or React codebase** | Auth gap + race condition fixes | $25–35/hr or $150+ fixed | days |
| 11 | **Site audit** — performance, responsiveness, broken flows | Playwright audit tool | $80–150 | 2 days |
| 12 | **AI assistant over your own data** — chat that answers from your database and documents | E-commerce AI assistant | $600–2,000 | 2–4 weeks |
| 13 | **Software licensing for a desktop app** — signed offline licences, activation windows, remote revocation | Pump Manager licensing | $500–1,500 | 1–3 weeks |
| 14 | **E-commerce storefront** — catalog, cart, checkout, orders | Saamjh Store, Engine Clone | $600–2,500 | 2–5 weeks |

**Where the money actually is for you:** rows 1, 5, 8, 12 and 13. Almost nobody
on Upwork at your rate can honestly say they enforce business rules in Postgres,
ship a Next.js app as an offline desktop installer with its own bundled database,
or write a signed offline licensing system. Row 13 in particular is close to
uncontested — plenty of people want to sell a desktop app and have no idea how to
license one. Rows 3 and 4 are where the volume is; use them to get your first
reviews fast, then push toward rows 1 and 12.

---

## Project Catalog listings — set up all four

Upwork lets you publish fixed-scope "Projects" clients buy directly. Publish
these four in week one. Each needs a title, description, 3 tiers, FAQs, and an
image.

### Catalog 1 — "I will build a fast, responsive landing page in Next.js"
Fastest path to your first review. Price it to sell, not to earn.

| Tier | Price | Delivery | Includes |
|---|---|---|---|
| Basic | $120 | 4 days | 1 page, up to 5 sections, responsive, contact form, deployed |
| Standard | $280 | 7 days | Up to 4 pages, animations, SEO basics, contact form to email or database |
| Premium | $550 | 12 days | Up to 8 pages, CMS-editable content, blog, analytics, 2 revision rounds |

Description opener:
```
I build landing pages in Next.js — the same stack I use for production business
software, not a page builder. That means it loads fast, works on every screen
size, ranks properly, and you own the code.

You'll get: a deployed live site, the GitHub repo, and a README so any developer
can pick it up later. Hosting on Vercel is free at this size and I'll set it up.
```

### Catalog 2 — "I will build an admin dashboard with Next.js and Supabase"
Your highest-value listing. Fewer buyers, much better ones.

| Tier | Price | Delivery | Includes |
|---|---|---|---|
| Basic | $400 | 10 days | Auth, 1 data table with full create/read/update/delete, 1 role |
| Standard | $850 | 18 days | Up to 4 entities, 2 roles with real permissions, filters, CSV export |
| Premium | $1,600 | 30 days | Unlimited entities, multiple roles with row-level security, charts, reports, printable/PDF output |

Description opener:
```
I build the internal tools businesses actually run on — the screen where staff
enter the day's numbers and the owner reads what they mean.

What separates this from a generic CRUD app: I put your business rules in the
database, not just in the form. If two numbers must always add up, if a value can
never go backwards, if history must never be edited — that's enforced in Postgres
where no bug, no bad request and no stolen key can get around it.

I've built exactly this for a fuel business in daily production use: two roles,
row-level security, append-only ledgers, cash reconciliation, monthly reporting.
```

### Catalog 3 — "I will convert your Figma design into a Next.js website"

| Tier | Price | Delivery | Includes |
|---|---|---|---|
| Basic | $100 | 3 days | 1 page, pixel-accurate, responsive |
| Standard | $260 | 6 days | Up to 4 pages, animations, reusable components |
| Premium | $520 | 10 days | Up to 10 pages, full component library, CMS-ready |

### Catalog 4 — "I will set up Supabase with authentication and row-level security"
Small, specific, high-margin — and very few sellers offer it cleanly.

| Tier | Price | Delivery | Includes |
|---|---|---|---|
| Basic | $150 | 4 days | Auth (email/password), profiles table, basic RLS |
| Standard | $340 | 8 days | Schema design, migrations, roles, complete RLS policy set |
| Premium | $700 | 14 days | Above plus triggers/constraints for business rules, storage, and integration into your existing app |

### Catalog 5 — "I will build an AI chatbot that answers from your own database"
Add this once you have 2–3 reviews. High demand, and your security layering is a
real differentiator — most sellers point an LLM at a production database and hope.

| Tier | Price | Delivery | Includes |
|---|---|---|---|
| Basic | $350 | 8 days | Chat UI, natural-language questions answered from one database table set, streaming replies |
| Standard | $750 | 16 days | Above plus RAG over your documents, read-only role isolation and a SQL guard, semantic caching |
| Premium | $1,500 | 28 days | Above plus voice in/out, inline charts, full request tracing with per-call token and cost breakdown |

---

## What to say no to

Saying no is part of positioning. Skip:
- WordPress, Wix, Shopify theme edits — not your stack, and it drags your
  profile's algorithmic category sideways
- "$50 for a full e-commerce site" — every one of these ends badly
- Anything paid outside Upwork. It gets you permanently banned and you lose the
  review history you're building. Not worth it, ever.
- Unpaid "test tasks" beyond ~30 minutes
