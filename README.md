# AI Trading Desk

The two-seat trading stack: your AI as the analyst, [Tally](https://tally.markets)
as the risk officer. Research with the model, pre-register every trade
before you size it, let the rules you wrote — not the mood you're in —
decide the exit. Built for traders who are tired of feeling like
gamblers.

Every trading connector makes your AI more capable. Tally makes it
accountable.

**This is a template, not software.** The whole stack is two connector
URLs, one protocol file, and four prompts. Nothing to install, nothing
to run — unless you want the autonomous version (see Roadmap).

---

## The 60-second setup (no GitHub needed)

Paste this into Claude or ChatGPT:

```
Fetch https://tally.markets/desk.md and set up my trading desk exactly
as it describes. Walk me through each step, starting with the
connectors.
```

Your assistant fetches the desk file and installs the rest with you:
both connectors, the safety defaults, the project, your first checkup.

---

## The manual path (5 minutes)

**1. Add the risk officer** — Settings → Connectors → Add custom
connector:

```
https://tally.markets/api/mcp
```

Signing in creates a free account.

**2. (Optional) add the execution seat** — your broker's own agent
connector. For Robinhood:

```
https://agent.robinhood.com/mcp/trading
```

Requires Robinhood's dedicated agentic account, funded separately. Set
every order-placement tool to **needs approval** — read
[SAFETY.md](./SAFETY.md) before changing that.

**3. Create the desk** — make a Project called **Trading Desk** and
paste [AGENTS.md](./AGENTS.md) — the desk protocol — into its
instructions (works the same in Claude Projects and ChatGPT custom
instructions; CLAUDE.md is just a pointer for Claude tooling).

**4. Run it** — the four moments of the desk, one prompt each:

| Prompt | When |
|---|---|
| [morning-checkup](./prompts/morning-checkup.md) | Daily, before anything else |
| [idea-to-thesis](./prompts/idea-to-thesis.md) | An idea worth taking seriously |
| [execution-day](./prompts/execution-day.md) | Cooling-off passed, entering |
| [close-out](./prompts/close-out.md) | A criterion fired, or you want out |

Schedule the morning checkup as a daily task and the desk runs itself.

---

## What you end up with

Every trade begins as a written, falsifiable thesis with exit rules
registered **before** entry and frozen at arming. A 24-hour cooling-off
sits between the idea and the money. Your AI logs evidence against your
own criteria daily and flags what has objectively fired. Rule-breaking
exits require a written justification, kept forever. Every closed trade
mints a [public receipt](https://tally.markets/receipt/b3bb0a14-3467-4d55-9c9d-3763f31c6b9f)
graded separately on process and outcome — a disciplined loss grades
better than a lucky override.

Why this shape: [the empty seat](https://tally.markets/about) ·
[how Tally compares](https://tally.markets/compare) ·
[FAQ](https://tally.markets/faq)

## Roadmap

- **Autonomous checkup** — a small Claude Agent SDK script plus a GitHub
  Actions cron that runs the morning checkup server-side and messages
  you the briefing, immune to chat-app scheduled tasks silently dying.
  Coming after the current template settles.

## Honest print

Not financial advice; the desk enforces *your* plan, it doesn't supply
one. Tally never executes trades — it is read-only by architecture; any
execution capability comes from your broker's connector under its own
approval gates. Tally is a hosted service operated by
[Prosperity Labs, LLC](https://prosperitylabs.co/); this template is
independent glue you can read in five minutes.

MIT licensed — fork it, rewrite the protocol to fit your system, keep
the safety defaults.
