# Safety defaults

This template ships conservative on purpose. Loosen anything below only
deliberately, after understanding what changes.

## Money

- **Fund only the dedicated agentic account.** Broker agent connectors
  (e.g. Robinhood Agentic) operate a separate account you fund
  explicitly — that balance is the most any agent can ever touch. Never
  point an agent at your main portfolio.
- **Order placement stays on "needs approval."** The agent stages;
  you place. Flipping a placement tool to always-allow means orders can
  execute while you are not looking. If you do it, do it knowingly, and
  size the account for that reality.
- **Size like it's real, because it is.** A template can't pick your
  risk. The thesis's own sizing rule is the ceiling; the agentic-account
  balance is the hard stop.

## Roles

- **Tally cannot trade.** It is read-only by architecture — it holds the
  record and enforces the process. Execution capability comes only from
  a broker connector you add yourself, or from nothing at all.
- **The protocol is not advice.** It enforces the plan you wrote. It has
  no opinion on what to buy, and neither does this repository.

## Hygiene

- Never paste API keys, passwords, or seed phrases into a chat, a
  prompt file, or this repo. Connectors authenticate through OAuth in
  your own browser; anything asking you to do otherwise is wrong.
- If you remove and re-add a connector, recreate any scheduled tasks —
  they silently bind to the old connector and stop running.
- The daily checkup is your heartbeat. If briefings stop arriving,
  treat it as broken until proven otherwise — silence is not "all
  clear." (Tally emails you if your checkup goes quiet for 72 hours,
  but don't outsource noticing.)
