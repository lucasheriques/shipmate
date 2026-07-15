---
name: continuous-discovery
description: Run post-launch product discovery using Continuous Discovery Habits (Teresa Torres) - opportunity solution trees, weekly interview cadence, assumption-level testing. Use when deciding what to build next for a live product, structuring or prioritizing a backlog of user needs, setting a product outcome or North-Star target for a team, turning interview notes into decisions, testing a feature idea before building it, or when shipped features aren't moving the metric.
---

# Continuous Discovery — post-launch discovery procedure

## When to use

A live product with real users, and the question is "what should we build next?" or "will this idea work?". This is the post-launch complement to The Mom Test: Mom Test validates whether a problem/business is real before building; this skill structures the ongoing loop of choosing and de-risking what to build once you have users. **For how to conduct the conversation itself (question technique, bad data, commitment), defer to the `mom-test` skill — it's stronger on that and this skill does not repeat it.**

## The procedure

### 1. Set one outcome

1. Pick a **product outcome**: a metric the team can move directly (e.g. "increase % of new users who reach the aha moment"), not a **business outcome** (revenue — lagging, cross-team) and not a **traction metric** (usage of one feature — too narrow). Prefer leading over lagging; iterate toward faster feedback (90-day retention → 5-day is a legitimate revision).
2. In a team: leader picks *which* outcome and shares the strategic why; the team commits *how much* movement ("+10% this quarter"). Neither side names solutions. Solo: still write the outcome down — it's the root of the tree and the referee of every later debate.
3. **One outcome at a time, kept for multiple quarters.** Pair it with a health metric so you don't optimize it destructively. New territory? Set a learning goal ("find the levers") before a numeric goal.

### 2. Map the opportunity space (the tree)

1. Draw an **experience map** of how customers do the job today. Scope it with a question calibrated to ambition: "How do people use *our product* to X" = optimization; "How do people X at all" = new markets. In a team, each person draws alone first, then merge (prevents groupthink). Visual — nodes (moments) and links.
2. Build the **opportunity solution tree**: outcome at the root; below it, opportunities = customer needs, pain points, desires **in the customer's own words**; below those, solutions; below those, assumption tests.
3. Construction rules — the tree's value is in following them strictly:
   - **Child = subset of parent. Siblings = similar but distinct** (you can address one without the others).
   - **Top-level opportunities = distinct moments in time** in the customer journey; branches must not overlap.
   - **No solutions in disguise** — test: "Is there more than one way to address this?" If not ("let me skip ads"), it's a solution; write the need behind it ("I don't like ads").
   - No company-perspective framings, no feelings-as-opportunities (capture the cause), no vertical single-child chains, no node that fits under two parents.
4. Feed the tree from interviews (step 3); it's never finished.

### 3. Interview weekly, synthesize continuously

1. **At least one customer interview every week.** The cadence is the deliverable; discovery done in bursts decays. Conduct per the `mom-test` skill (story-based: "tell me about the last time you…", specifics over speculation).
2. **Automate recruiting** so the interview schedules itself: in-product intercept ("Do you have 20 minutes to talk to us? $20 gift card" → scheduling link); triggers for support/sales colleagues ("customer asks about X → offer an interview"); or, for low-traffic/B2B/hard-to-reach segments, a standing **customer advisory board** (~12 people for a weekly cadence) interviewed monthly in rotation.
3. Write a one-page **interview snapshot** immediately after each interview: memorable verbatim quote · quick facts (segment, context) · opportunities heard, in their words · insights · a mini map of their specific story. Feature request? Ask "If you had that, what would it do for you?" and record the answer, not the feature. Snapshots are the searchable knowledge bank that feeds the tree.

### 4. Pick one target opportunity

1. Compare **sibling opportunities only** — first the top level, pick a branch, ignore the rest, recurse down to a **leaf**. Never assess one opportunity yes/no in isolation.
2. Four lenses, qualitatively: **sizing** (how many customers × how often), **market** (table stakes vs differentiator), **company** (strategy/strengths fit), **customer** (importance × satisfaction with current solutions — prioritize important + poorly served).
3. No weighted scoring formulas — they create false certainty. It's a reversible (two-way-door) decision: time-box to an hour or two, pick, move.

### 5. Generate solutions — then test assumptions, not ideas

1. Ideate against the ONE target opportunity: alone → share → alone (groups brainstorming together produce less), until **15–20 ideas**. Dot-vote (criterion: how well it addresses the target opportunity) down to **3 candidate solutions**. Tests, not opinions, pick the final winner.
2. For each candidate, surface **20–30 assumptions** across five categories — desirability, viability, feasibility, usability, ethical — via: **story-mapping** the not-yet-built solution (each actor's steps to get value; assumptions per step); a **pre-mortem** ("it's 6 months out and this failed completely — what went wrong?"); walking the tree lines ("this solution addresses the opportunity because…"); and an explicit harm check (data use, exclusion, abuse, front-page test). Phrase every assumption so you need it TRUE.
3. **Assumption-map** each idea in ≤10 minutes: importance (y) × strength of evidence (x), plotted relatively. Test only the **2–3 leap-of-faith assumptions** in the important-and-unevidenced corner.
4. Test = **Simulate → Evaluate**: simulate the *smallest possible moment* (fake-door link, one-question survey about past behavior, unmoderated prototype task, data-mine existing usage), and measure **behavior**, never stated intent.
5. **Pre-commit pass criteria as counts, never percentages**: "at least 3 of 10 do X" — written down before data arrives. Run the first test on the friendliest audience (a failure there is unambiguous). Escalate test size only on signal. Triangulate important assumptions with more than one test type.
6. Expect and welcome failed tests — that's hours spent instead of weeks. Kill the solution (or the opportunity: not every real need deserves solving), return to step 4 or 5, and keep moving. Stop testing when the remaining risk is cheaper to retire by just building.

### 6. Ship, measure, loop

1. Instrument only what's needed: this week's tests → the product outcome → the outcome→business link. **Count people vs actions** rule: if one person doing it many times isn't as valuable as many people doing it once, count people.
2. Record **expected impact before shipping; compare with actual after.** The gap is next quarter's best discovery argument — and the trigger to revisit the tree.
3. In an org, **show your work**: walk stakeholders through the tree top-down (outcome → opportunities → choice → solutions → tests), inviting input per layer. Never open with the conclusion — that invites an opinion battle with the highest-paid person. Their pet idea: story-map it together so its assumptions surface, or park it on the tree visibly.

## Quick reference

**Well-formed tree** — one measurable outcome at root · opportunities in customer words · siblings distinct, children subsets · top level = moments in time · no solutions in disguise · exactly one target leaf.

**Honest test** — criteria pre-committed, in counts · simulates a moment, measures behavior · friendliest audience first · one measure per step of multi-step behavior.

**Actually continuous?** — interviewed within 7 days · recruiting runs itself · snapshot per interview · can name outcome, target opportunity, and 3 candidate solutions from memory · expected-vs-actual recorded for the last ship.

**Solo translation** (the book assumes a PM+designer+engineer trio in a mid-size org): the trio collapses to "get design and engineering perspectives before deciding"; skip the stakeholder chapter until you have a boss, board, or client; everything else (tree, interviews, assumption tests) works as-is. The "15–20 discovery iterations/week" figure is aspiration, not a bar — several assumption tests a week is the real habit.

## Source

Compiled from *Continuous Discovery Habits* — Teresa Torres (2021). The skill is the procedure; the book carries the depth (worked examples, edge cases, the author's reasoning). If this stage is where your venture lives right now, buy and read it.
