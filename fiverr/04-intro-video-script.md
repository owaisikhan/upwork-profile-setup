# Fiverr intro video — script & shot list

Target: **60 seconds**. Fiverr's hard cap is 75 — don't use it all. Nobody
watches a full 75-second seller video, and the last 15 seconds are where people
click away.

## Fiverr's rules — a video that breaks these gets rejected

- **No contact details.** No email, phone, WhatsApp, website, or social handles,
  spoken or on screen. Check the screen recording for a browser bookmarks bar.
- **No prices or rates.** Not spoken, not on screen.
- **No external links or logos** of other platforms.
- **Show your face**, at least at the start. Fiverr weights this and buyers
  respond to it.
- Speak English throughout. Accent is fine — clarity matters, polish doesn't.

## Before recording: the data problem

The screen recording carries the same risk as the screenshots. Either:
- Set `BUSINESS_NAME` in `app/_lib/brand.js` to something invented and point at
  a dev database with fake data, **or**
- Only record screens where the sidebar is the sole identifier, and blur it in
  post — which Bilal can do, since he can edit.

**Never film the Customers page or the Activity log.** Real names and phone
numbers in a public video can't be un-published.

---

## The script

Word counts are tuned to ~150 words/minute. Bilal should read it once out loud
and adjust anything that doesn't sound like him — a script he's fighting sounds
like a script.

### [0:00 – 0:08] ON CAMERA

> "Hi, I'm Bilal. I build the software small businesses actually run on —
> dashboards, internal tools, and web apps."

*Look at the lens, not at yourself. Slight smile. This is the only shot most
people judge you on.*

### [0:08 – 0:19] SCREEN RECORDING — Dashboard

> "This is a management system a petrol station uses every single day. Their
> whole business is in here — daily takings, fuel stock, customer credit,
> and profit."

*Slow cursor move across the four stat cards. No clicking yet.*

### [0:19 – 0:33] SCREEN RECORDING — Daily readings, then Sale & Stock Register

> "Staff type in the meter readings each evening. The app works out what was
> sold, splits it into cash and credit, and tells the owner what should be in
> the drawer — before he counts it."

*Click into Readings, scroll one nozzle card into view, then cut to the register
and let the gain/loss column sit on screen for a beat.*

### [0:33 – 0:41] SCREEN RECORDING — Reports

> "At the end of the month, one page: sales, costs, profit, and a spreadsheet
> for the accountant."

*Land on the profit figure. Hover the Download Excel button — don't click.*

### [0:41 – 0:51] BACK ON CAMERA

> "I build these in Next.js and Supabase. Admin dashboards, business web apps,
> marketing sites, and Figma designs turned into real, working code."

### [0:51 – 1:01] ON CAMERA — close

> "Send me a message with what you're trying to build, and I'll tell you
> honestly whether I'm the right person for it. Thanks for watching."

*Stop recording two seconds after you finish speaking. Don't trail off, don't
wave, don't say "bye guys".*

**Total: ~60 seconds, ~150 words.**

---

## Shot list

| # | Shot | Length |
|---|---|---|
| 1 | On camera — opening | 8s |
| 2 | Screen — Dashboard | 11s |
| 3 | Screen — Readings → Sale & Stock Register | 14s |
| 4 | Screen — Reports | 8s |
| 5 | On camera — stack and services | 10s |
| 6 | On camera — close | 10s |

Record shots 1, 5 and 6 in one sitting, same clothes, same framing. Record the
screen separately at 1080p, then cut it in underneath the voice.

## Production notes

- **Framing:** head and shoulders, eyes on the upper third, plain wall behind.
  Same background as the profile photo if possible — it reads as consistent.
- **Light:** face a window. Nothing behind you brighter than your face.
- **Audio matters more than video.** Phone earbuds close to the mouth beat a
  laptop mic across a room. Record somewhere with soft furnishings; a bare tiled
  room sounds like a bathroom.
- **Screen recording:** 1080p, clean browser — no bookmarks bar, no other tabs,
  no notifications. Move the cursor slowly and deliberately. Fast cursor movement
  reads as nervous.
- **Cuts:** hard cuts only. No swipes, no zoom transitions, no whooshes. This is
  a developer's video, not a reel — restraint reads as senior.
- **Music:** either none, or something flat and quiet at about 10% under the
  voice. If it competes with the words, it's too loud.
- **No captions burned in** unless the audio is genuinely hard to follow. Fiverr
  shows the video small.
- **Export:** MP4, 1080p, under 50 MB.

## The thing worth saying to Bilal

He already knows how to do all of this. The temptation will be to make it good —
colour grade it, add motion graphics, cut it fast. Resist that. A developer's
intro video that looks like an ad reads as a marketer pretending to code. The
edit should be invisible: clean audio, steady framing, hard cuts, nothing else.

The skill shows up as the absence of mistakes, not the presence of effects.
