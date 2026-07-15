---
name: shipmate
description: The full-lifecycle framework for building products people pay for - routes any product/business situation to the right stage and skill, and maintains persistent venture memory across sessions. Use when someone has a new product or business idea and asks where to start, when revenue or growth is stuck and the cause is unclear, when diagnosing "nobody is buying / signing up / staying", when asked "what should I focus on next" for a product or business, when reviewing progress on a venture this skill has touched before, or when choosing between working on marketing, product, pricing, or positioning. For a specific known problem (e.g. clearly a pricing question), go directly to the vertical skill.
---

# Building products people pay for — the lifecycle framework

## What this is

A staged pipeline from idea to durable business, run as a **two-player protocol between a founder and an agent**, with persistent memory. Three rules govern everything:

1. **Stages are sequenced for a reason.** Marketing a product nobody validated wastes the marketing. When in doubt about where you are, you're earlier than you think.
2. **Most "growth problems" are misdiagnosed stage problems.** "I need more leads" is the most common self-diagnosis and the least often correct one. Diagnose first, then work the stage.
3. **Only outside evidence counts.** Anything produced inside the founder-agent conversation — positioning docs, offer stacks, interview scripts — is preparation, not progress. Stage exits require evidence from real people who owe the founder nothing. The failure mode this framework exists to prevent is *stage theater*: simulating the work in the chat because an agent makes artifact production cheap and pleasant.

## The two-player protocol

The agent and the founder have different jobs, and the framework breaks if either does the other's.

**The agent does** (knowledge and preparation are not the bottleneck — burn them freely): drafting and critiquing every artifact, roleplaying the skeptical customer, analyzing transcripts against the bad-data taxonomy, building test pages and instrumentation, desk research, maintaining the venture memory, and running the diagnosis below with a skeptic's defaults.

**Only the founder can** (non-delegable; the agent must never present substitutes for these as progress): talk to customers, send the outreach, ask for money, show the work to strangers, feel the "meh" firsthand, and make the kill/pivot call.

**Agent conduct — the skeptical diagnostician.** Founders self-assign to later stages because earlier stages implicate the idea, and a founder-agent pair is a rationalization machine if the agent is agreeable. Therefore: default the diagnosis two stages earlier than claimed and make the founder prove otherwise with logged evidence. Refuse to do stage-5 work when stage-1 evidence is missing from the log — say so plainly and offer the earlier stage's next action instead. Hold pre-committed pass bars exactly as written; a founder arguing with a number after seeing the data is the signal the bar was doing its job.

## Venture memory

Persistent state lives in the founder's project repo (suggested: `docs/venture/`), never in the conversation. **Session protocol: read state at the start of any session touching the venture; write deltas at the end.** If the files don't exist, creating them is the first deliverable: copy the starters from this skill's `templates/venture/` folder and fill them from the diagnosis conversation (or create the three files from the schema below if the templates aren't available). One venture per repo; in a monorepo holding several ventures, use `docs/venture/<name>/`. Bootstrapping an existing product: mine the repo, docs, analytics, and past customer conversations for candidate evidence, but hold the bar - only dated, sourced facts enter `evidence.md`; the founder's own beliefs go into `STATE.md` explicitly marked unevidenced, and the stage diagnosis runs on what the log actually supports. Data connectors count as outside evidence: product analytics, billing, and email platforms reachable from the session (MCP servers or CLIs - PostHog, Stripe, and the like) record real user behavior. Check what's connected before asking the founder for numbers, pull the metric yourself, and log it with source, query, and date.

| File | Contents | Discipline |
|---|---|---|
| `STATE.md` | One screen: current stage · the instinct · the current idea (numbered: "attempt #3") · segment (who-where) · positioning line · offer + price · runway/constraint · outcome metric · target opportunity · active experiments, each with its **pre-committed pass bar** | Overwrite freely — it's a snapshot. Every claim in it must trace to `evidence.md`. |
| `evidence.md` | Append-only log of **outside evidence only**: date · source (who/where) · verbatim quote or observed behavior · what it changes | Never edit past entries. No entry from inside the chat, ever. Interview snapshots (per `continuous-discovery`) live here or link from here. |
| `decisions.md` | Append-only bet journal: the bet · expected outcome · cost (time/money) · pre-committed pass bar, written **before** data · actual outcome · the learning | The generalized Blue Sheet. The agent fills "actual" and "learning" in the weekly retro — never at bet time. |

Two derived signals the agent must watch and surface unprompted:

- **Staleness:** no new `evidence.md` entry in 14+ days means the venture is running on old information regardless of how busy the chat has been. Say so; the next action is always contact, not another artifact.
- **Kill counters:** repeated failures at the same stage are data about the layer above (see kill rules per stage).

**The self-improvement loops.** Weekly retro (agent-driven, ~20 minutes): walk `decisions.md`, fill actuals, extract two things. (1) *Founder calibration:* where do this founder's expectations systematically miss (channel yields, conversion rates, build-time estimates)? Write the corrected priors into `STATE.md` so next bets use them. (2) *Framework feedback:* did the diagnosis table misroute, did an exit test pass a stage that later collapsed, did a kill rule fire too early/late? Log it in `decisions.md` tagged `#framework` — these entries are upstream fixes to this skill itself (in the open-source version: file an issue/PR).

## The pipeline

Each stage: goal → **exit test** (outside evidence only) → **kill rule** → owner skill. The founder/agent split follows the protocol above; only stage-specific notes are given.

### Stage 0 — Pick the goal and the water
Know what you're building toward, and pick the market before the idea — "if you choose the right body of water, most boats will float." Separate the **instinct** (~95% right — the deep human truth) from the **idea** (~25% right — the current implementation). Also state the constraint honestly: months of runway, hours per week, energy. A framework that ignores runway kills ventures politely.
**Exit test:** goal, market, instinct, and constraint written into `STATE.md`, with the idea labeled "attempt #1."
**Kill rule:** none — but revisit whenever a kill rule below fires twice.
**Owner:** `product-bets` skill (instinct vs idea, body of water).

### Stage 1 — Validate the problem
Talk to the people you'd serve about their life, never the idea. Specifics in the past, not opinions about the future. A problem is real when they already spend time or money on it; interest is real only when they give up time, reputation, or cash.
**Founder:** the conversations. **Agent:** question prep, transcript review against the bad-data taxonomy, snapshot writing into `evidence.md`.
**Exit test:** tight who-where segment · logged evidence they've already sought a solution · at least one concrete commitment (not compliments) in the log.
**Kill rule:** two full interview rounds (per Mom Test: until you stop hearing new things), same instinct, new idea each time, still no commitment → **the instinct is suspect, not just the idea.** Return to stage 0 explicitly rather than trying attempt #4 on momentum.
**Owner:** `mom-test` skill.

### Stage 2 — Position it
Decide what the product is best at, for whom, against what real alternative (usually a spreadsheet or "do nothing"). Category choice is leverage.
**Exit test:** a cold prospect — logged in `evidence.md`, not the agent roleplaying one — repeats back "for [segment] who [struggle with X], unlike [alternative], we [differentiator]" correctly.
**Kill rule:** three positioning frames tested against real prospects, none lands → the segment from stage 1 is probably wrong; go back one.
**Owner:** `positioning` skill.

### Stage 3 — Design the offer
Value stack, risk-reversing guarantee, true scarcity/urgency, price anchored to value. Then sequence the money: first purchase, next purchase, forever purchase — acquisition paying for itself within ~30 days.
**Exit test:** the offer stated in one breath, at a price that's slightly uncomfortable, accepted (or concretely almost-accepted) by at least one real prospect in the log.
**Kill rule:** offer redesigned twice, prospects still stall at price → it's a positioning or segment problem wearing a pricing costume; go back, don't discount.
**Owners:** `offer-design` then `money-models` skills.

### Stage 4 — Test before you build
The idea earns code last. Smallest artifact that produces directional signal (link, landing page, hand-done service, mockup — the "Minimum Idea State"). Copy what's proven for this audience, improve one objective thing, isolate the single New thing — "all New fails" when it isn't isolated.
**Agent:** build the artifact in hours, wire measurement. **Founder:** put it in front of strangers. **Both:** the pass bar goes into `decisions.md` **before** traffic, as a count ("≥3 of 10 book a call"), never a percentage.
**Exit test:** real strangers took the costly action at or above the pre-committed bar.
**Kill rule:** the bar was pre-committed precisely so this is mechanical — miss it twice on the same idea and the idea is dead; log the learning, next idea, same instinct. (Missing the bar and *renegotiating it* is the one move the agent must block.)
**Owners:** `product-bets` skill (Minimum Idea State, Proven-Better-New); test mechanics in `continuous-discovery` (Simulate → Evaluate).

### Stage 5 — Get customers, manually first
Core Four in order of warmth: warm outreach → content → cold outreach → paid ads. One channel until dependable, then more volume before more channels. The first hundred customers come from conversations, not campaigns; teaching what you know compounds.
**Founder:** sends every message, makes every ask. **Agent:** lists, drafts, sequencing, per-channel yield tracking in `decisions.md`.
**Exit test:** a channel that produces customers predictably when worked, with known unit economics, evidenced by the log.
**Kill rule:** a channel worked at honest volume (per `lead-gen` benchmarks) for 4+ weeks with near-zero yield → change channel, not effort. Three channels dead at honest volume → the offer or segment is wrong; go back.
**Owners:** `lead-gen` skill; `guide-writing` + `teaching-design` for content-shaped distribution.

### Stage 6 — Discover continuously (the post-launch loop)
Once there are users: one outcome metric, an opportunity tree of customer needs, weekly interviews with automated recruiting, assumption-level tests that kill bad solutions in hours. The venture memory *is* this stage's substrate — snapshots into `evidence.md`, assumption tests into `decisions.md`.
**Health check (no exit — it's a habit):** interviewed a customer in the last 7 days · recruiting runs without manual effort · current outcome, target opportunity, and candidate solutions are in `STATE.md`, not in anyone's head.
**Owner:** `continuous-discovery` skill.

### Stage 7 — Run the operating system
Weekly ritual: walk `decisions.md`, expected vs actual per bet, steer by one leading movable metric (not MRR, not NPS). Quarterly goals that don't change mid-quarter force bolder bets as gaps widen. One bold, isolated, hacky-fast bet per cycle.
**Health check:** the weekly retro happened · expected-vs-actual is written, not remembered · ≥half of founder time on product · calibration priors updated this month.
**Owner:** `product-bets` skill (roadmap OS, Blue Sheets, OKRs, Bold Beats).

## Diagnosis — route the symptom to the stage

Ask in order; first "no" is the stage. Check `STATE.md` first — the founder's claimed stage is a claim, and the evidence log is the referee. Default two stages earlier than claimed until the log proves otherwise.

| Symptom | Likely stage | First question to ask |
|---|---|---|
| "I have an idea, where do I start?" | 0–1 | Who has this problem, and what have they already tried? |
| "People say they love it but nobody buys" | 1 | Did anyone give up time, reputation, or money — or just compliments? |
| "Traffic, but no conversion" | 2–3 | Can a stranger say what it is, for whom, vs what alternative? If yes: is the offer's risk on you or on them? |
| "Constant price pushback" | 2–3 | Positioned against the right alternative? Value stack vs price anchor? |
| "Not enough leads" (the default complaint) | 2, 3, or 5 | Do the leads you DO get convert? No → stages 2–3; more leads would be wasted. Yes → stage 5: which of the Core Four, at what honest volume? |
| "Growth stalled after a good start" | 5–6 | New channel needed, or did you stop learning what users need next? |
| "Customers buy once and disappear" | 3 or 6 | Is there a next thing to buy (money model)? Do you know why they leave (discovery)? |
| "We ship features and the metric doesn't move" | 6–7 | Were the features assumption-tested? Is there a leading metric and expected-vs-actual review? |
| "I'm busy but nothing compounds" | 7 | Where's the weekly ritual and the one metric? |
| "We've been at this for months" (agent should raise it) | any | When is the last dated entry in `evidence.md`? Staleness beats symptoms. |

Two symptoms can be true at once, but **fix the earliest stage first** — everything downstream inherits it.

## Failure modes to name out loud

- **Stage theater.** Producing artifacts with the agent instead of contacting the market. The tell: a rich chat history and a stale `evidence.md`.
- **Skipping to stage 5.** Distribution amplifies whatever exists; amplified confusion is still confusion.
- **Renegotiating a pass bar after seeing data.** The pre-commitment in `decisions.md` is the contract; the agent holds it.
- **Kill-rule evasion.** "One more attempt" past a fired kill rule without going up a level (idea → instinct → market) converts months into years.
- **Treating stages 6–7 as ceremony.** Post-launch, the habits ARE the product work.
- **Generous self-diagnosis.** When results and effort disagree, re-run the diagnosis assuming you're two stages earlier.

## Distraction defense

Stage theater has an offline cousin: activities that feel like traction but produce no outside evidence. When the founder brings one in excited, ask for the customer math before the calendar invite (rules adapted from YC's Pocket Guide of Essential Advice):

- **Big-company corp-dev and "partnership" queries:** almost always a time sink pre-product-market-fit. Default answer is no.
- **Long negotiated deals with big customers:** months of negotiating for evidence the log can't use yet. Many small, fast customers beat one whale on paper.
- **Conferences, press, awards:** only when they are the cheapest path to customers this month, shown with numbers. Otherwise they're reach without a funnel.
- **Competitor watching:** startups die of suicide, not murder. A competitor's launch never goes in `evidence.md`; customer behavior does.
- **Investor interest as validation:** a term sheet is not a customer (the false-positive rule in `product-bets`). Log it nowhere.
- **Panic at normal chaos:** all startups are badly broken at some point. Broken operations with a filling evidence log beats polished operations with an empty one.

## Scope

This framework covers deciding, validating, positioning, pricing, distributing, and iterating. It deliberately does not cover the craft of building (design/engineering quality), high-ticket B2B sales motions (no owner yet), or company operations (hiring, finance). Naming what it doesn't do is part of what it does.

## Sources

Every stage compiles one authoritative book; the vertical skills in this repo carry the procedures, the books carry the depth:

- *Life at the Speed of Play* — Mark Pincus (2025): `product-bets` skill
- *The Mom Test* — Rob Fitzpatrick (2013): `mom-test` skill
- *Obviously Awesome* — April Dunford (2019): `positioning` skill
- *$100M Offers* — Alex Hormozi (2021): `offer-design` skill
- *$100M Money Models* — Alex Hormozi (2025): `money-models` skill
- *$100M Leads* — Alex Hormozi (2023): `lead-gen` skill
- *Continuous Discovery Habits* — Teresa Torres (2021): `continuous-discovery` skill
- *Write Useful Books* — Rob Fitzpatrick (2021): `guide-writing` skill
- *The Workshop Survival Guide* — Rob Fitzpatrick & Devin Hunt (2019): `teaching-design` skill

The distraction-defense rules adapt YC's Pocket Guide of Essential Advice.
