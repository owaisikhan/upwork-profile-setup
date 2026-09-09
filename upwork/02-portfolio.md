# Portfolio items — Bilal Sagheer

Two groups: **his own work** (items 1–5) and **team projects he collaborates on**
(items 6–8). Add his own first — they carry his name honestly and answer the
"walk me through how you built this" question without qualification.

For every team project, tick Upwork's **"I worked on this with others"** option
and lead the description with his actual role. Reasoning in `06-team.md`.

> Screenshots decide whether a card gets read. Take 3–4 clean captures per item
> at 1440px with real content, and blur client data.

---

## 1. Laravel + Vue admin panel with roles and permissions

**One-liner:** Single-page admin panel on Laravel and Vue 3 with multi-role user
management, granular permissions and an elegant, minimal interface.

**Long description:**
```
A complete admin panel built as a single-page application: Laravel 10 on the
back, Vue 3 and Inertia on the front, so it behaves like an SPA without the
overhead of maintaining a separate API and front-end app.

WHAT'S IN IT
• Multi-role user management — create roles, assign granular permissions, and
  have the interface reflect what each role can actually do
• Authentication built on Laravel Jetstream: registration, password reset,
  two-factor, session management, API tokens
• Media handling with image processing and S3-compatible storage
• Rich text editing, searchable and paginated data tables, sortable listings
• Ziggy for route handling, so the front end and back end never disagree about
  a URL

WHY THIS SHAPE
Most projects that need an admin panel need the same eight things and then one
unusual one. This is built so the eight are already done and the ninth is a
clean place to add. Roles and permissions in particular are the part people
underestimate — "admin and user" becomes five roles and thirty permissions
about three weeks into every project.

Stack: Laravel 10, Vue 3, Inertia.js, Jetstream, Vite, Vuex, Tailwind CSS,
MySQL, AWS S3.
```
**Skills:** Laravel · Vue.js · PHP · MySQL · Web Application · API Integration

---

## 2. Automation engine with LLM integration

**One-liner:** Event-driven trigger-action automation framework with OpenAI and
Anthropic integrations, agentic tool-calling and MCP servers — powering multiple
production products.

**Long description:**
```
The automation layer several products run on. When something happens in the
system, the right thing happens next — without a person doing it.

THE ENGINE
An event-driven trigger-action framework: define what counts as a trigger, define
what should follow, and the engine handles the sequencing, the retries and the
failures. This is the piece that replaces "someone remembers to check the
spreadsheet on Monday".

THE AI LAYER
Language models wired into real workflows rather than dropped in as a chat box:
• Integrations against both the OpenAI and Anthropic Claude APIs
• Agentic workflows — prompt orchestration and tool-calling, so the model can
  actually do things in the system rather than only describe them
• Model Context Protocol tools and servers, giving assistants a defined,
  constrained set of capabilities instead of open-ended access

WHY IT MATTERS FOR YOUR PROJECT
Most "add AI" requests are really automation requests with a language model
somewhere in the middle. The value is in the workflow around the model —
what triggers it, what it's allowed to touch, what happens when it's wrong —
and that's the part I build.

Stack: PHP/Laravel, Node.js, Python, OpenAI API, Anthropic Claude API, Model
Context Protocol, Redis, event-driven architecture.
```
**Skills:** AI Integration · Automation · Laravel · Python · Node.js · API Integration

> **Note for Bilal:** this is your strongest card and the least visible on
> GitHub, because the work sits in private product repos. Write it up carefully
> and be ready to talk through the architecture on a call — that's what will
> convert it.

---

## 3. eBay product data scraper

**One-liner:** PHP scraper that runs an eBay search, walks every result, and
extracts full detail for each product.

**Long description:**
```
A data extraction tool for eBay: give it a search, and it works through every
result in the listing and pulls the full detail record for each product rather
than just what the search page shows.

The interesting problems in scraping are never the parsing. They're the pacing
that keeps you from being blocked, the retry logic for the requests that fail
anyway, handling listings whose structure isn't quite like the others, and
resuming a run that died three thousand products in without starting over.

I build these to run unattended and produce clean, structured output you can
load straight into a database or spreadsheet.

I also do this for other sources — product catalogs, price monitoring,
directories, listings. If you can see it in a browser, it can usually be
collected properly.

Stack: PHP, HTTP clients, HTML parsing, structured data export.
```
**Skills:** Web Scraping · PHP · Data Extraction · Automation

---

## 4. Laravel setup package

**One-liner:** Reusable Composer package that does a Laravel project's standard
setup in one command instead of an afternoon.

**Long description:**
```
An internal package published to Composer that handles the boilerplate every new
Laravel project needs — the configuration, the scaffolding and the commands that
otherwise get copied by hand from the last project and slowly drift out of sync.

It's a small thing, and it's the kind of small thing that says how someone works.
Doing the same setup by hand twenty times is a choice; noticing and packaging it
is a different one.

I build this kind of internal tooling for teams: shared packages, project
scaffolding, and the conventions that stop five developers writing five versions
of the same helper.

Stack: PHP, Laravel, Composer package development.
```
**Skills:** Laravel · PHP · Package Development

---

## 5. Hotel management API

**One-liner:** Laravel REST API backing a hotel management system, with a
separate Vue admin front end.

**Long description:**
```
A Laravel REST API for hotel operations, with a Vue.js admin dashboard consuming
it as a separate application.

Split that way deliberately: the API serves the admin panel today and can serve a
mobile app or a booking widget tomorrow without being rewritten. When the front
end and the API are one codebase, the second consumer is always a rewrite.

The dashboard side is built on Vuetify with Vuex for state, drag-and-drop
ordering, date-range filtering and a component structure meant to be extended.

Stack: Laravel, PHP, MySQL, Vue.js, Vuetify, Vuex, REST API design.
```
**Skills:** Laravel · REST API · Vue.js · PHP · MySQL

---

## Team projects — mark these as collaborations

Bilal works with two other developers, Owais Khan and Ammar Sagheer, on a
Next.js + Supabase product line. These are legitimate portfolio items **as long
as his role is stated**. Fill in his real contribution before publishing — I've
left the role line explicit rather than guessing at it.

---

## 6. Petrol station management system (team project)

**One-liner:** Business management system in daily production use — daily meter
readings, stock, customer credit ledgers, cash reconciliation and monthly profit.

**Long description:**
```
My role: [FILL IN — e.g. "project coordination and delivery management, plus
work on X"]. Built with two other developers.

A complete operations system for a petrol station, replacing a stack of paper
registers and one enormous spreadsheet. Staff enter each nozzle's closing meter
reading; the system computes litres and value at the day's rate, splits the day
into cash and credit, and tells the owner what cash should be in the drawer
before it's counted — so a mismatch is caught while it's still fixable.

Covers daily readings, fuel purchases and tank dips, lubricant stock and counter
sales, per-customer credit ledgers, the physical cash in the safe with a running
balance, bank accounts, expenses, assets and monthly profit reporting.

Two roles, enforced properly: staff can enter the day's trade but never see
profit, expenses or bank balances — enforced in Postgres row-level security, in
a role check on every server action, and in the navigation.

The money rules live in the database, not the form: cash plus credit must equal
what the meter sold; a meter can never run backwards; two readings for one nozzle
can't overlap and double-count litres; the customer ledger is append-only, so a
mistake is corrected by an offsetting entry rather than by editing history.

It also ships as a licensed offline Windows application with its own bundled
Postgres, for businesses without reliable internet.

Stack: Next.js, React, Supabase (Postgres, Auth, RLS), Material UI, Tailwind,
Electron.
```
**Skills:** Project Management · Web Application · PostgreSQL · Next.js
**→ Tick "I worked on this with others."**

---

## 7. E-commerce AI assistant (team project)

**One-liner:** Storefront chatbot that answers product, price and policy
questions by generating SQL against the live catalog, with RAG, voice and
semantic caching.

**Long description:**
```
My role: [FILL IN]. Built with two other developers.

A shopper asks a question in plain language — typed or spoken — and gets an
answer streamed back live.

Product, price and stock questions are answered by an LLM writing a SQL query
against the real catalog, running it, and summarising the result, with a
self-healing retry if the query fails. Policy questions are answered from
retrieved store documents via RAG. Answers worth charting render as charts.

The security model is the point. Letting a model write SQL against a production
database is dangerous unless it's constrained in layers: the backend connects as
a Postgres role with SELECT on exactly three tables — orders, addresses,
profiles and wishlists are unreachable whatever the model generates — and a SQL
guard rejects anything that isn't a single read-only SELECT before it reaches
the database at all.

Questions are embedded and matched against past questions by cosine similarity;
a close match returns the cached answer with no model call at all. Only
successful answers are cached, so a transient failure never gets stuck as the
permanent answer. Every request is traced with latency, a per-step breakdown and
the token cost of each model call.

Stack: Next.js, LangGraph, Google Gemini, Postgres + pgvector, Redis, Langfuse.
A Python/FastAPI variant of the same pipeline also exists.
```
**Skills:** AI Integration · LangChain · Python · PostgreSQL · API Integration
**→ Tick "I worked on this with others."**

---

## 8. Offline desktop business software with licensing (team project)

**One-liner:** Next.js business applications packaged as installable Windows
programs with bundled Postgres, sold under a signed offline licence.

**Long description:**
```
My role: [FILL IN]. Built with two other developers.

Two products shipped this way: the petrol station system, and a committee
manager for running a rotating savings group.

Web apps need internet, a server and a monthly bill. These install from an .exe,
keep their books in a Postgres database bundled inside the application, and never
need a connection.

Selling software that runs entirely offline means you can't check a server before
letting someone in, so licences are signed tokens verified locally with Ed25519.
Each has an activation window and a support date; past that date the app soft-
restricts — new entries refused, every existing record still readable and
exportable, because a client who stops paying should never lose access to their
own books. When a machine does have internet, the app checks a published blocked-
key list on its existing update schedule.

Stack: Next.js, React, embedded Postgres, Electron, electron-builder,
Ed25519 signing.
```
**Skills:** Electron · Desktop Application · PostgreSQL · Software Licensing
**→ Tick "I worked on this with others."**

---

## Also worth a mention in the overview, not as cards

- **API gateway** work (`bill-api-gatway`)
- **Vue.js admin dashboards** — Vuetify, Vuex, drag-and-drop, date filtering
- **CodeIgniter** legacy work — useful, since a real slice of Upwork PHP jobs are
  maintaining CodeIgniter apps nobody wants to touch. Low competition.
