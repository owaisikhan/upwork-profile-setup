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

## Collaboration — the "collaborator" evidence

You asked about projects you're a collaborator on. What's actually on the record:

- **`Ammar-Sagheer/Pump-manager-releases`** — you're a contributor to the release
  and licensing repo for the pump product, including designing the online
  licence-restriction check (an installed client's app phones home on its
  existing update-check schedule; a blocked key is soft-restricted — new entries
  refused, existing data still readable and exportable).
- **Pull-request workflow on `pump-manager-display`** — four PRs from a
  collaborator's branches reviewed and merged by you, covering UI restyles and a
  server/client boundary crash across six pages.

Don't make a portfolio card out of this. Instead, put one line in your overview
and use it in proposals when a client asks whether you can work in a team:

```
I work in a normal team workflow — feature branches, pull requests, code review.
On my current product I'm both the reviewer merging collaborators' PRs and a
contributor to a separate release/licensing repo.
```
