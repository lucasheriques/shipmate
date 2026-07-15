# Shipmate

**The mate who helps you ship.**

Every AI agent is a yes-man. Ask it about your startup idea and it will draft you a beautiful positioning doc, a landing page, and a go-to-market plan — for an idea nobody wants. A founder plus an agreeable agent is a rationalization machine.

Shipmate is a set of agent skills that makes your AI act like the experienced companion a first-time founder actually needs: it carries proven frameworks for every stage from idea to durable business, keeps a persistent log of what the market actually said, holds you to the numbers you committed to before you saw the data — and refuses to help you skip ahead.

## What makes it different

Skill packs give your agent **knowledge**. Shipmate gives it a **spine**:

- **A two-player protocol.** The agent drafts, critiques, builds test pages, analyzes transcripts, keeps the books. Only you can talk to customers, send the outreach, and ask for money — and the agent is instructed to never present chat artifacts as progress. The failure mode Shipmate exists to prevent is *stage theater*: simulating a startup inside the conversation.
- **Outside evidence only.** Every stage has an exit test, and only evidence from real people who owe you nothing counts. The agent tracks it in an append-only log in your repo.
- **Venture memory.** `STATE.md` (where you are), `evidence.md` (what the market said, dated, verbatim), `decisions.md` (every bet: expected vs actual, with pass bars written *before* the data). Pre-commitment only binds if it's persisted — that's the whole trick.
- **Kill rules.** Every stage defines when to stop trying harder and go back a level (idea → instinct → market). "One more attempt" past a fired kill rule is how months become years.
- **A skeptical diagnostician.** The agent defaults to assuming you're two stages earlier than you claim, and makes you prove otherwise from the log. "I need more leads" is the most common self-diagnosis and the least often correct one.

## The pipeline

| Stage | Question | Skill / source |
|---|---|---|
| 0 | What's the goal, the market, the instinct — and the runway? | *Life at the Speed of Play* |
| 1 | Is the problem real? | `mom-test` |
| 2 | What is this, for whom, against what alternative? | `positioning` |
| 3 | Is the offer irresistible — and does the money sequence work? | `offer-design`, `money-models` |
| 4 | Did strangers act, before you built it? | *Life at the Speed of Play* + `continuous-discovery` test mechanics |
| 5 | Is there a channel that produces customers when you work it? | `lead-gen` (+ `guide-writing`, `teaching-design` for content) |
| 6 | Do you know what to build next — from evidence? | `continuous-discovery` |
| 7 | Does the weekly operating system run? | *Life at the Speed of Play* |

The entry point is the `shipmate` skill: it diagnoses your stage from your symptom and routes you to the right vertical. Each vertical skill is compiled from one authoritative book (full list in [Sources](#sources)) — the skill is the procedure, the book is the depth.

## Quickstart

Shipmate is plain-markdown [Agent Skills](https://agentskills.io) — they work with Claude Code and any agent that reads `SKILL.md` files.

```bash
git clone https://github.com/lucasheriques/shipmate.git
# Claude Code: symlink the skills into your skills directory
ln -s "$(pwd)/shipmate/skills/"* ~/.claude/skills/
```

Then, in your project:

1. Start a conversation: *"I have an idea for X, where do I start?"* — or, for an existing product, *"revenue is stuck, diagnose it."* The `shipmate` skill triggers, runs the diagnosis, and routes you.
2. Let it create `docs/venture/` from the [templates](templates/venture/) — that's the memory. From then on, every session starts by reading `STATE.md` and ends by writing deltas.
3. Do your half: the calls, the outreach, the asks. The log fills with outside evidence, or it stays empty and the agent tells you the uncomfortable thing.

## Contributing scars

The routing table improves from real misroutings, not opinions. If Shipmate diagnosed your stage wrong, passed you through an exit test that later collapsed, or fired a kill rule at the wrong time — [file a misrouting report](.github/ISSUE_TEMPLATE/misrouting.md). Anonymize freely; the failure pattern is the contribution.

## Sources

Shipmate compiles procedures from books that earned their place — one authoritative book per stage, chosen over their overlapping competitors:

- *The Mom Test* — Rob Fitzpatrick (2013)
- *Obviously Awesome* — April Dunford (2019)
- *$100M Offers* / *$100M Leads* / *$100M Money Models* — Alex Hormozi (2021/2023/2025)
- *Life at the Speed of Play* — Mark Pincus (2025)
- *Continuous Discovery Habits* — Teresa Torres (2021)
- *Write Useful Books* — Rob Fitzpatrick (2021)
- *The Workshop Survival Guide* — Rob Fitzpatrick & Devin Hunt (2019)

The skills condense and cite; they don't reproduce. If a stage matters to your business, buy the book — every one of these authors earned it.

## License

[MIT](LICENSE). The frameworks belong to their authors; the compilation, protocol, and memory system are free to use, fork, and adapt.
