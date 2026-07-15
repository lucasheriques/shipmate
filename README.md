# Shipmate

[![skills.sh](https://skills.sh/b/lucasheriques/shipmate)](https://skills.sh/lucasheriques/shipmate)

**The mate who helps you ship.**

Every AI agent is a yes-man. Ask one about your startup idea and ten minutes later you have a landing page and a go-to-market plan for a product nobody asked for. A founder plus an agreeable agent is a rationalization machine.

Shipmate turns your agent into the companion a first-time founder actually needs. One proven framework per stage, from idea to durable business. A log of what the market actually said. And a standing refusal to let you skip stages or bend the numbers you committed to before seeing the data.

## What makes it different

Skill packs give your agent knowledge. Shipmate gives it a spine.

- **A two-player protocol.** The agent drafts, critiques, builds test pages, and keeps the books. Only you can talk to customers and ask for money. Chat artifacts never count as progress: simulating a startup inside the conversation (we call it stage theater) is the exact failure mode Shipmate exists to prevent.
- **Outside evidence only.** Every stage has an exit test, and it passes only on evidence from real people who owe you nothing. Nothing produced inside the chat gets in.
- **Venture memory.** `STATE.md` says where you are. `evidence.md` records what the market said, dated and verbatim. `decisions.md` holds every bet with its pass bar written before the data existed. Pre-commitment only binds when it's written down.
- **Kill rules.** Every stage defines when to stop trying harder and question the level above: first the idea, then the instinct, then the market. "One more attempt" past a fired kill rule is how months become years.
- **A skeptical diagnostician.** The agent assumes you're two stages earlier than you claim until the log proves otherwise. "I need more leads" is the most common self-diagnosis founders make, and the least often correct one.

## The pipeline

| Stage | Question | Skill |
|---|---|---|
| 0 | What's the goal, the market, the instinct, and the runway? | `product-bets` |
| 1 | Is the problem real? | `mom-test` |
| 2 | What is this, for whom, against what alternative? | `positioning` |
| 3 | Is the offer irresistible, and does the money sequence work? | `offer-design`, `money-models` |
| 4 | Did strangers act, before you built it? | `product-bets` + `continuous-discovery` test mechanics |
| 5 | Is there a channel that produces customers when you work it? | `lead-gen` (+ `guide-writing`, `teaching-design` for content) |
| 6 | Do you know what to build next, from evidence? | `continuous-discovery` |
| 7 | Does the weekly operating system run? | `product-bets` |

The entry point is the `shipmate` skill: it diagnoses your stage from the symptom you bring and routes you to the right vertical skill. Each vertical is compiled from one authoritative book (full list in [Sources](#sources)). The skill is the procedure; the book is the depth.

## Quickstart

Shipmate is plain-markdown [Agent Skills](https://agentskills.io). It works with Claude Code, Cursor, Codex, and any agent that reads `SKILL.md` files.

```bash
npx skills add lucasheriques/shipmate -s '*' -y
```

Install all ten. Shipmate is one system, not a menu: the `shipmate` skill diagnoses your stage and hands off to the other nine by name, so a partial install breaks the routing.

Prefer doing it by hand? Clone and symlink:

```bash
git clone https://github.com/lucasheriques/shipmate.git
# Claude Code: symlink the skills into your skills directory
ln -s "$(pwd)/shipmate/skills/"* ~/.claude/skills/
```

Then, in your project:

1. Start a conversation. "I have an idea for X, where do I start?" works. So does "revenue is stuck, diagnose it." The `shipmate` skill triggers, runs the diagnosis, and routes you.
2. Let it create `docs/venture/` from the [templates](skills/shipmate/templates/venture/), which ship inside the `shipmate` skill. That's the memory. From then on, every session starts by reading `STATE.md` and ends by writing what changed.
3. Do your half: the calls, the outreach, the asks. The log fills with outside evidence, or it stays empty and the agent tells you the uncomfortable thing.

## Using it day to day

Shipmate triggers when your prompt sounds like a founder question. Prompts that work:

**Starting something**
- "I have an idea for a Chrome extension that does X. Where do I start?"
- "Bootstrap the venture memory for this project. Here's everything I know so far."
- "This product already exists. Bootstrap the venture memory: mine the repo, the docs, and the data I give you. Only dated, sourced facts go in `evidence.md`; flag every claim in `STATE.md` that has nothing behind it, then diagnose my real stage."

**Stuck**
- "Revenue has been flat for two months. Diagnose it."
- "People hit the landing page and nobody signs up. What stage am I actually at?"

**Customer calls** (the most important loop in the system)
- "I have a call with a potential customer tomorrow. Prep me: what are the three things we need to learn, and what question could kill the idea?"
- "Roleplay the customer so I can practice not pitching."
- "Here's today's call transcript. Separate real signal from compliments, fluff, and feature requests, then write the snapshot for `evidence.md`."
- "They said they loved it and to check back next month. Did that meeting succeed or fail?"

**Before building anything**
- "I want to build [feature]. Surface the assumptions and design the cheapest tests."
- "Write the pass bar for this experiment before I run it."

**Getting customers**
- "I need more customers. Which of the four channels should I be working, and what does an honest week of volume look like?"
- "Prospects keep saying it's too expensive. Is that a price problem, an offer problem, or a positioning problem?"

**The weekly retro**
- "Run the weekly retro: walk `decisions.md`, fill in actuals, update my priors."

**Honesty checks**
- "BigCo's corp dev wants a call. Worth it?"
- "Read the venture memory and tell me what I'm avoiding."
- "Six months in. Read the whole log and tell me if a kill rule has fired."

### Making it stick (context engineering)

Skills fire on phrasing, and you won't always phrase things like a founder. Two lines of setup make the system unconditional:

1. Add to your project's `CLAUDE.md` or `AGENTS.md`: *"Venture memory lives in `docs/venture/`. Read `STATE.md` before any product, pricing, or marketing work. The shipmate protocol applies: outside evidence only, hold my pass bars, tell me when I'm doing stage theater."*
2. Commit `docs/venture/` to the repo. The memory is only as durable as its storage, and an agent in a fresh session recovers the whole venture from those three files.

Worth knowing:

- One venture per repo. A monorepo with several products gets a `docs/venture/<name>/` each.
- Evidence is a dated, verbatim quote with a source: `2026-07-14, Joao (cold DM): "I'd pay for this today, can I?"`. "Users liked it" doesn't qualify.
- The agent is instructed to assume you're two stages earlier than you claim. When it refuses to write ad copy and asks about your evidence log instead, that's the product working.

## Contributing scars

The routing table improves from real misroutings, not opinions. If Shipmate diagnosed your stage wrong, passed you through an exit test that later collapsed, or fired a kill rule at the wrong time, [file a misrouting report](.github/ISSUE_TEMPLATE/misrouting.md). Anonymize freely. The failure pattern is the contribution, not your product's details.

## Sources

One authoritative book per stage, picked over its overlapping competitors:

- *The Mom Test*, Rob Fitzpatrick (2013)
- *Obviously Awesome*, April Dunford (2019)
- *$100M Offers* / *$100M Leads* / *$100M Money Models*, Alex Hormozi (2021/2023/2025)
- *Life at the Speed of Play*, Mark Pincus (2025)
- *Continuous Discovery Habits*, Teresa Torres (2021)
- *Write Useful Books*, Rob Fitzpatrick (2021)
- *The Workshop Survival Guide*, Rob Fitzpatrick & Devin Hunt (2019)

The skills condense and cite. They don't reproduce the books. If a stage matters to your business, buy the book: every one of these authors earned it.

## License

[MIT](LICENSE). The frameworks belong to their authors; everything Shipmate adds on top is free to use, fork, and adapt.
