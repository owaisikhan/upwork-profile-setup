# Portfolio items — 6 entries, ready to paste

Upwork shows portfolio as cards: **title, one-line description, long
description, skills, image**. Add these in this order — the first three carry
the most weight.

Every project below is real work from your GitHub. Where a project was built for
a family business rather than a paying client, the wording says "in daily use"
and never says "client engagement". That's deliberate — it stays true and still
reads as production software, which is what matters.

> **Screenshots matter more than the text.** A card with no image gets skipped.
> For each live URL below, take 3–4 clean screenshots (desktop, 1440px wide,
> real data not lorem ipsum) and upload them. For the pump system, blur or
> replace real figures and names before uploading anything.

---

## 1. Petrol Station Management System — daily operations, stock & ledgers

**One-liner:** Full business management system for a fuel station: meter
readings, stock, customer credit, cash reconciliation and monthly profit.

**Long description:**
```
A complete operations system for a petrol station, in daily production use.

It replaces a stack of paper registers and one enormous spreadsheet. Staff enter
each nozzle's closing meter reading in the evening; the system works out litres
and value at today's rate, splits the day into cash and credit, and tells the
owner what cash should be in the drawer — before it's counted, so a mismatch is
caught while it's still fixable.

WHAT IT COVERS
• Daily nozzle readings with opening figures carried forward automatically
• Fuel purchases, tank dip readings and lubricant stock, with gain/loss tracking
• Per-customer credit ledgers — slips are recorded against the customer and
  their balance updates itself
• Lubricant counter sales, cash or credit, onto the same ledger
• Treasury: the physical cash in the safe, one line per movement with a running
  balance, reconciled against the notes rather than against another screen
• Bank accounts, expenses, company assets
• Monthly profit reporting and an exportable workbook

TWO ROLES, ENFORCED PROPERLY
Owner and data-entry staff. Staff can enter the day's trade but never see profit,
expenses, bank balances or the safe. That's enforced in three independent places:
Postgres row-level security policies (the real protection), a role check at the
top of every server action, and the navigation (cosmetic only). No email is
hardcoded anywhere — roles live in the database.

THE RULES LIVE IN THE DATABASE
This is a money tool, so the constraints are in Postgres where application code
can't get around them: cash + credit must equal what the meter sold; a meter can
never run backwards; two readings for one nozzle can't overlap and double-count
litres; the customer ledger is append-only — a mistake is corrected by posting an
offsetting entry, never by editing history. Enforced by triggers, not permissions.

WHITE-LABELLED
Business name and logo are one config file and one image. Change them and the
sidebar, login screen, browser tabs and monthly workbook all follow — no code
change. Built to be resold to the next station.

Stack: Next.js 16 (App Router), React 19, Material UI, Tailwind CSS v4,
Supabase (Postgres + RLS + Auth), Recharts, Vercel. Also ships as an offline
Windows desktop build.
```
**Skills:** Next.js · Supabase · PostgreSQL · React · Material UI · Database Design · Web Application

---

## 2. Meridian Consulting — website with AI intake funnel and admin dashboard

**One-liner:** Consulting firm site with a multi-step AI-assisted lead intake
form and a private admin dashboard for managing enquiries.
**Live:** https://merdian-consulting.vercel.app

**Long description:**
```
A consulting firm's public site plus the private tool that runs behind it.

The public side is a fast, animated marketing site. The part that earns its keep
is the intake funnel: a multi-step form that takes contact details, then adapts —
the follow-up questions change based on which service the visitor picked, so
nobody is asked twelve irrelevant questions. It ends in a review-and-submit step
so the lead sees exactly what they're sending.

Behind a login sits an admin dashboard where the firm works its leads: filter,
sort, and move each enquiry through its status. Google's Gemini is wired in
through the Vercel AI SDK to assist on the intake side, with Zod validating
every payload before it reaches the database.

Auth is a real auth gate, not a hidden route — I found and fixed an admin
authorisation gap and a login race condition during the build, and the fixes went
in through a reviewed pull request.

Stack: Next.js 16, React 19, Supabase (Auth + Postgres), Vercel AI SDK with
Google Gemini, Zod, GSAP, Tailwind CSS v4, Vercel.
```
**Skills:** Next.js · Supabase · AI Integration · React · Web Development · Landing Page

---

## 3. Core Stack — 45-page commerce platform marketing site

**One-liner:** Production-fidelity rebuild of an omnichannel commerce platform's
marketing site — 45 pages, real design tokens, real typography.

**Long description:**
```
A ~45-page marketing site for a cloud commerce platform (POS, ecommerce,
customer app, warehouse management and ERP in one product), rebuilt as a real
Next.js application from a design-system handoff.

Routes: home, 5 solution pages, 5 industry pages, and 27 business-type pages
(POS / ecommerce / app crossed with grocery, clothing, bakery, cafe, barbershop,
beauty salon, tyre shop, pet services, cleaning services) — all generated from
structured content rather than hand-built one at a time. Plus blog, contact,
live demo, about and legal pages.

The interesting constraint was fidelity. Spacing, colour and type come from the
design system's own token files and production CSS class names, not from
approximate Tailwind utilities — so the result matches the source pixel-close
instead of "close enough". All copy, images and font declarations came through
the pipeline; nothing was retyped by hand, which is what kept 45 pages accurate.

Content and navigation live in two config modules, so the whole site can be
rebranded by editing one file and swapping two logos.

Stack: Next.js 16, React 19, Tailwind CSS v4, CSS design tokens.
```
**Skills:** Next.js · React · Web Development · Landing Page · Responsive Design · UI/UX Design

---

## 4. The Ledger — Android app for offline ledger entry

**One-liner:** React Native / Expo Android app that records daily business
entries offline on a local SQLite database and prints or shares PDF reports.

**Long description:**
```
The mobile companion to the station system, for a phone in a hand at the pump.

Built on Expo with expo-router. The whole thing works with no internet: entries
are written to a local SQLite database on the device, so a dropped connection
never costs a day's data. Reports are generated on-device and can be printed or
shared straight out as PDFs.

Ships as a real installable Android APK through EAS Build — not a web page in a
wrapper. The repo includes its own verification scripts that check the SQL and
every screen before a build goes out, plus a scripted screenshot pass.

Stack: React Native, Expo (expo-router, expo-sqlite, expo-print, expo-sharing),
EAS Build.
```
**Skills:** React Native · Mobile App Development · SQLite · JavaScript

---

## 5. PSX RSI Dashboard — stock screener as a Windows desktop app

**One-liner:** Swing-trading dashboard for the Pakistan Stock Exchange —
RSI across ~750 equities, packaged as an installable Windows application.

**Long description:**
```
A screener for a specific trading strategy: find oversold stocks, hold one to
two weeks, sell. Not a general-purpose charting tool.

It computes RSI for every listed PSX equity at a selectable look-back period
(14 / 5 / 2, each with its own oversold and overbought thresholds) and chart
interval, matching TradingView's own RSI to within normal vendor-data noise.

The engineering problem was load. Firing ~750 requests at PSX's feed at once
isn't viable, so it loads the KSE-100 index stocks first — the ~100 companies
that actually matter appear fast — with everything else behind a "Load more".
Illiquid stocks are filtered out by a volume floor. Refresh re-prices what's
loaded and recomputes RSI without re-crawling all history.

Also has a buy-signal screener on a fixed rule, per-row insight that reads
whatever period and interval you're currently looking at, a starred watchlist
persisted locally, and a market-breadth summary.

Packaged with Electron and electron-builder into a signed-off Windows installer
that runs as a normal desktop program.

Stack: Next.js 16, React 19, Recharts, Electron, electron-builder, Tailwind v4.
```
**Skills:** Electron · Next.js · React · Data Visualization · Desktop Application · API Integration

---

## 6. Fast Pizza Co. — React ordering app with cart and live order tracking

**One-liner:** Restaurant ordering app: menu, cart, address capture, order
placement and live order lookup, with Redux Toolkit state and currency handling.

**Long description:**
```
A complete food-ordering flow built in React with Vite.

Browse the menu, build a cart, enter delivery details, place the order, then
look the order up again by ID to track it. State runs through Redux Toolkit with
separate slices for cart, user and currency — including live currency conversion,
which is the kind of thing that looks trivial until prices start disagreeing with
each other across screens.

Routing and data loading use React Router's loader/action model, so data is
fetched at the route level rather than in effects scattered through components.
Supabase is wired in for persistence.

Stack: React 19, Vite, Redux Toolkit, React Router 7, Tailwind CSS v4, Supabase.
```
**Skills:** React · Redux · JavaScript · Tailwind CSS · Web Development

---

## Also worth mentioning (in the overview, not as cards)

- **The Wild Oasis** — cabin booking site: date-range availability picker,
  guest accounts, reservation management. Next.js 16 + Supabase + NextAuth v5 /
  better-auth. Live: `the-wild-oasis-thechamps.vercel.app`
- **Roaster Site** — coffee shop site built to a design handoff in TypeScript.
  Live: `coffee-shop-2-nu.vercel.app`
- **Core Stack console** — POS checkout, inventory and order-management screens
  against a 22-component design system. Live: `services-thechamps.vercel.app`
- **Site audit tool** — small Playwright script that crawls a site and reports
  problems. Good evidence you automate your own QA.

## Joint work with Ammar Sagheer

These come out of the shared repos. **Mark every one of them as a collaboration
on Upwork and lead the description with your role** — the reasoning is in
`06-partnership.md`. Several of the source repos are private and some have real
clients behind them, so clear each with Ammar before publishing, and blur real
figures and names in screenshots.

---

### 7. Petrol Pump Manager (Desktop) — offline Windows app with commercial licensing

**One-liner:** The petrol station system as an installable Windows program that
runs with no internet, on its own bundled Postgres, behind a signed licence.

**Long description:**
```
My role: I built the licensing system end to end, and ported the web application
to the desktop build — the read layer, the write layer, the reporting, the Excel
export and the UI. Built with a development partner, who leads the product side.

The web version needs internet and a Supabase account. Plenty of businesses have
neither reliably. So this is the same system as a normal Windows program: it
installs from an .exe, keeps its books in its own bundled Postgres inside the
install directory, and never needs a connection to do its job.

THE LICENSING, WHICH IS THE HARD PART
Selling software that runs entirely offline means you cannot check a server
before letting someone in. So:
• Licences are Ed25519-signed tokens, verified locally. Forging one means
  forging a signature, not editing a config file.
• Each licence has an activation window and a support date. Past the support
  date the app soft-restricts: new entries are refused, but every existing
  record stays readable and exportable. A client who stops paying never loses
  access to their own books — that's deliberate, and it's the difference between
  a licence check and a hostage situation.
• A licence can be renewed from inside the app, without a restart or reinstall.
• Each install marks its own records with its initials.
• When a machine does have internet, the app checks a published blocked-key list
  on its existing update-check schedule — which is what actually reaches a client
  who stays offline on purpose to dodge a restriction. Local clock checks alone
  are trivially defeated by changing the clock.
• The whole issue-and-block procedure is written down as a checklist, so
  supporting a customer doesn't depend on remembering how it works.

Everything from the web version came across: nozzle readings and their overlap
rules, the lubricant shelf and its reports, loose-oil handling with its own
export split, customer removal and purging, the activity log, and a multi-sheet
Excel export.

Stack: Next.js, React, embedded Postgres, Electron, electron-builder,
Ed25519 signing.
```
**Skills:** Electron · Next.js · PostgreSQL · Desktop Application · Software Licensing · Node.js

---

### 8. Committee Manager — offline desktop app for a rotating savings group

**One-liner:** Windows app for running a monthly committee (ROSCA): contributions,
payouts, flexible repayments, and a solvency forecast that says what's actually
affordable.

**Long description:**
```
Built with a development partner for a man managing a committee of ten.

A committee is a rotating savings pot: ten people each pay in monthly, and each
month one of them takes the pot and repays it over the following months on top
of his ordinary contribution.

THE PROBLEM THE APP EXISTS FOR
With ten members the turn comes round every ten months, but a withdrawal is
repaid over fifteen. So full-size payouts go out while the repayment stream
behind them is still building — and the gap is invisible from the bank balance.
On the real numbers, an account holding Rs 520,000 looks comfortable right up to
the month it empties. The app simulates the whole schedule month by month and
binary-searches for the largest payout that never breaches the safety cushion —
then, when the answer is no, sizes the three ways out: pay less, repay faster,
or everyone contributes more. It distinguishes "you cannot afford this" from
"you cannot afford this yet", because they have different answers.

THE BOOKS CANNOT DRIFT
The rules are triggers, constraints and functions in Postgres, not form
validation. The ledger is append-only — a mistake is corrected by writing the
opposite entry, and both stay visible. A withdrawal larger than the account
holds is refused outright with no override. One that breaches the cushion is
refused too, but that's policy rather than physics, so it goes through if the
manager types a reason — and the reason is kept forever and reprinted on the
month's summary for the other nine to read. A repayment can't exceed what's
owed. Nothing posts into a closed month.

Members' stakes always add up to exactly the money in the account, because the
stake isn't stored anywhere — it's one sum read two ways. A verification script
asserts that identity after every operation.

Runs fully offline as an installed Windows program with its own bundled Postgres.

Stack: Next.js, React, embedded Postgres, Electron, iron-session, Recharts.
```
**Skills:** Electron · PostgreSQL · Next.js · Desktop Application · Financial Software · Database Design

---

### 9. E-commerce AI assistant — natural-language product search over a live catalog

**One-liner:** Storefront chatbot that answers product, price and policy
questions by generating SQL against the real catalog, with RAG, voice and a
semantic cache.

**Long description:**
```
Built with a development partner for an e-commerce storefront.

A shopper asks a question in plain language — typed or spoken — and gets a real
answer streamed back token by token, not a wait-then-dump.

HOW IT ANSWERS
• Product, price and stock questions: an LLM writes a SQL query against the
  actual product catalog, runs it, and summarises the result. If the query
  fails, it self-heals and retries once.
• Policy questions (shipping, returns, payment): answered from retrieved store
  documents via RAG, not from the database.
• Answers worth charting (comparisons, trends) render as an inline bar or line
  chart.
• It can speak the answer back through the same streaming pipeline.

THE SECURITY MODEL, WHICH IS THE POINT
Letting a language model write SQL against your production database is a
genuinely dangerous idea unless you constrain it properly, in layers:
• The backend connects as a dedicated Postgres role with SELECT granted on
  exactly three tables — products, categories, product_images. Orders,
  addresses, contacts, profiles and wishlists are unreachable no matter what
  SQL the model produces.
• A SQL guard rejects anything that isn't a single read-only SELECT against the
  allowed tables, before it reaches the database at all.
• The endpoint requires a shared-secret API key and CORS is origin-restricted.

PERFORMANCE
Questions are embedded and compared against past questions by cosine similarity;
a match at 0.87 or above returns the cached answer with no SQL generation, no
database round-trip and no summarisation call. Only genuinely successful answers
are cached — a failed self-heal never gets stuck as the permanent answer.

Every request is traced: latency, a per-step breakdown, and the token count and
estimated cost of each model call. Works with no account and no network; adding
Langfuse keys ships the same traces to a dashboard.

Stack: Next.js, LangGraph, Google Gemini (generation, embeddings, transcription,
text-to-speech), Postgres + pgvector via Supabase, Redis (Upstash), Langfuse.
A Python/FastAPI variant of the same pipeline also exists.
```
**Skills:** AI Integration · LangChain · Next.js · PostgreSQL · Python · API Integration · Chatbot Development

---

### 10. Saamjh Store — e-commerce storefront (ask Ammar before publishing)

Private repo with a real client behind it (`saam-s-store`, `saam-s-store-client1`).
From the schema the AI agent reads against, it has products, categories, product
images, orders, addresses, customer profiles, contacts and wishlists on Supabase
Postgres — a complete store, not a catalog page.

**Only add this once Ammar confirms the client is fine with it**, and describe
your role accurately. If the answer is no, that's fine — you have nine other
entries and the AI assistant above already demonstrates the same stack.

---

### Also in the shared portfolio

- **Engine Clone** — full storefront: category listings, product detail pages,
  search endpoint, cart drawer and cart page, with state in React Context +
  `localStorage` via `useSyncExternalStore`. Next.js 16 App Router, plain JS.
  Honest as a practice build; good evidence of e-commerce front-end.
- **Hotel Management App** — the admin side of the booking system: React Query,
  react-hook-form, styled-components, Recharts dashboards.

## What to say when a client asks about teamwork

```
I work in a normal team workflow — feature branches, pull requests, code review.
On the product I build with my development partner I'm both the reviewer merging
his PRs and the author of our licensing system and desktop port. If your project
needs more capacity than one person, we can take it on together.
```
