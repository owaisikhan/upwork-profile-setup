# Working with Ammar — how to put joint work on Upwork

You said to treat Ammar's repos as yours. Here's how to do that so it's both
true and strong — because the honest version is genuinely better than the
overclaimed one.

## What the git record actually shows

You are not a bystander on Ammar's repos. Across `Ammar-Sagheer/*` you have 38
commits, and they are not typo fixes:

- **You built the entire offline licensing system** for the pump product —
  Ed25519-signed licence tokens, an activation window, soft restriction after
  the support date expires, in-app licence renewal without a restart, and
  per-install initials marking. You also wrote `docs/LICENSING_WORKFLOW.md`,
  the checklist for issuing and blocking a client's licence.
- **You built the online blocked-licence check** (`Pump-manager-releases`) —
  an installed client's app phones home on its existing update-check schedule;
  a blocked key is soft-restricted, so new entries are refused while existing
  data stays readable and exportable. That is the mechanism that actually
  reaches a client who stays offline to dodge a support-date restriction.
- **You ported the entire web app to the offline desktop build** — read layer,
  write layer, the reading-overlap rules, the lubricant shelf and its reports,
  loose-oil handling and its export split, customer removal and purging, the
  activity log, the Excel export, and the whole UI (sidebar nav, lubricant
  screens, paging).
- **You review and merge his work** — six PRs on
  `Petrol-Pump-Management-Software`, covering unit replacement, forecourt
  rearrangement, a stock-valuation fix, table density and row-level editing.
- He builds for you too — `Ammar-Sagheer/Portofolio-Website` has the package
  name `owais-khan-portfolio`.

That is a real two-person product team shipping a **commercially licensed
desktop product**. Very few people at your rate can say that.

## So say exactly that

You don't need to claim you wrote every line. "I built the licensing and the
desktop port on a product my partner and I ship commercially" is stronger than
"I made this app", because it's specific, it's verifiable, and it survives the
question a good client always asks: *walk me through how you built this.*

**Upwork has a built-in mechanism for this.** When you add a portfolio item
there's a "I worked on this with others / collaborators" option. Use it, and put
your role in the first line of the description. It costs you nothing and it
protects you — an item flagged as collaborative with a clear role reads as
professional, while an unflagged one that a client later finds on someone else's
GitHub reads as a lie. That second outcome ends contracts.

## The bigger move: an Upwork Agency

If you and Ammar are working together going forward, the right structure is an
**Upwork Agency**, not two separate freelancer profiles quietly sharing a
portfolio.

- One of you creates the agency; both join it. You keep your individual profiles
  as well, so you can still bid solo.
- An agency can legitimately show **all** the team's work as agency work. The
  problem you're trying to solve disappears entirely.
- You can bid on bigger projects. A two-person team can credibly take a $3,000
  build that neither of you would bid on alone at your current review count.
- One person handles client comms while the other builds — which is what
  actually kills part-time freelancers.

**Cost:** free to create. Upwork's agency fee is the same 10%.

**When to do it:** after you each have 2–3 reviews on your individual profiles.
A brand-new agency with zero history is harder to sell than a freelancer with
zero history, because clients expect an agency to have a track record. Get your
first reviews solo, then form the agency and carry them across.

**Split the pitch:** don't market as "two Next.js developers" — that's just one
developer twice. Market as *"we build and ship business software: one of us on
the product and data layer, one on the client-facing build."* Two people who do
the same thing is a discount; two people who cover a pipeline is a team.

## Rules that keep this safe

1. **Never present a project Ammar built alone as yours.** Mark it collaborative
   and state your role, or leave it off.
2. **Ask him before you publish anything from his private repos.**
   `Petrol-Pump-Management-Software`, `Offline-Petrol-Pump-Manager`,
   `saam-s-store`, `saam-s-store-client1` and `Coffee-Shop-Website` are private.
   Some have real clients behind them. Client work usually can't be shown
   publicly without permission — and `saam-s-store-client1` is somebody's actual
   store.
3. **Blur real data in every screenshot.** Customer names, balances, phone
   numbers, licence keys. This applies to the pump system especially.
4. **Agree who owns what commercially**, in writing, before you're earning.
   The pump product is a licensed commercial product with real installs. Who
   owns it, how income splits, what happens if one of you stops — settle it now
   while it's easy and friendly. This is the single most common way partnerships
   between friends go bad, and it is entirely preventable.
5. **Don't both bid on the same job from separate profiles.** Upwork treats that
   badly and clients notice immediately.
