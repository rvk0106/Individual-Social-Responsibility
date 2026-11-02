# Civic reporting app — concept note

> Idea from 2026-11-02, right after the first complaint (`CPR-BillVistaVillas/`).
> Not started. Target: build slowly over 1–1.5 years, after the CCFA certification.

## Why — Individual Social Responsibility

Vamsi: *"This is not corporate social responsibility, it is individual social
responsibility — taking care of the small things around me and trying to live
peacefully."*

The problem: there is no public place where civic issues and how fast they get
resolved are visible. *"If a government resolves more issues, people will feel
like voting for it. Until now we have no place to measure which government
develops better, where there are fewer issues."*

## The idea

1. A citizen sees a problem → records a video, tags the location, posts it
   (Instagram/Facebook-style feed).
2. **First-level check by an AI agent:** is the issue real, which rule is broken,
   which office owns it.
3. **Admin confirms**, then a proper complaint letter goes to the right office
   (the way the 2026-11-02 complaint was built by hand: evidence → rules → letter).
4. **Public scorecard:** issues and resolution time by ward / zone / corporation /
   constituency. The data creates the accountability.

## What already exists (checked 2026-11-02)

| Platform | Where | What it lacks for this idea |
|---|---|---|
| MyCURE (replaced MyGHMC, Feb–Mar 2026) | GHMC, Hyderabad | Private complaints, no public scorecard, no verification layer |
| Puramitra (was PuraSeva) | Andhra Pradesh | Same; routing problems reported |
| GHMC WhatsApp 81259 66586 | Hyderabad | Sanitation / C&D only |
| Solve Ninja (Reap Benefit) | Bengaluru NGO | Closest model: youth reporters, campaigns; Karnataka focus |
| FixMyStreet (mySociety) | UK, open source | Public map + council response; Perl/Catalyst, PostgreSQL + PostGIS, Open311, AGPL-3.0 (license per a third-party listing — confirm in the repo) |

**What is new here:** the verification layer before anything is sent, the
auto-drafted formal letter, and the public scorecard by government body.

## Stack (Vamsi's choice)

- **React** (web), **React Native** (mobile, Expo), **Ruby on Rails** (backend).
- PostgreSQL + PostGIS (`activerecord-postgis-adapter`) for location data.
- Claude for the verification step.
- First version: a mobile-friendly web page + WhatsApp intake, no app-store app.
- If any FixMyStreet code is reused, AGPL means the platform must be open source too.

## Risks to design for

- **Political neutrality** — show data, not opinions.
- **Defamation** — publish only verified facts; careful with builder and personal names.
- **Reporter privacy** — the complainant's name and home never shown.
- **Fake and duplicate reports** — the reason for the verification layer.

## How it grows

- Start with the schools Vamsi visits: children and parents report issues around
  their school (potholes, garbage, traffic, construction dust) — civic education
  for them, first users for the app.
- MVP test: 20–30 real complaints from Nallagandla / Tellapur on a map with status,
  before building the app.
- Trust built this way also serves the long goal: parents trusting him for a
  future school.

## Open

- Name.
- Repo rename to `Individual-Social-Responsibility` — Vamsi to do in GitHub settings.
- Design and architecture session (suggested on the most capable model) when the build starts.
