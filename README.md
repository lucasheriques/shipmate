# Shipmate

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
npx skills add lucasheriques/shipmate
```

Prefer doing it by hand? Clone and symlink:

```bash
git clone https://github.com/lucasheriques/shipmate.git
# Claude Code: symlink the skills into your skills directory
ln -s "$(pwd)/shipmate/skills/"* ~/.claude/skills/
```

Then, in your project:

1. Start a conversation. "I have an idea for X, where do I start?" works. So does "revenue is stuck, diagnose it." The `shipmate` skill triggers, runs the diagnosis, and routes you.
2. Let it create `docs/venture/` from the [templates](templates/venture/). That's the memory. From then on, every session starts by reading `STATE.md` and ends by writing what changed.
3. Do your half: the calls, the outreach, the asks. The log fills with outside evidence, or it stays empty and the agent tells you the uncomfortable thing.

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
