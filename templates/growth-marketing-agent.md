# AGENTS.md – Growth Marketing Agent Template

## Overview

- Use this file in a repo where the agent runs marketing work: cold email, landing pages, paid ads, content.
- The agent reads, drafts, measures, and reports. A human sends, publishes, and spends.
- Every test gets a declared volume and a kill rule **before** the first unit is spent. No exceptions, including "just a quick look".

## Environment

- Node 22 LTS for tooling. `npx` runs the test maths with no install step.
- Draft copy lives in the repo (`campaigns/`, `landing-copy/`). Nothing is sent from the agent session.
- One CSV per test under `experiments/`, plus `experiments/index.md` as the ledger.
- Credentials come from environment variables. Never commit a key, never paste one into a draft.

## Test Volume Floors

Below the floor you are reading randomness, not the market. Declare the floor, then run one variable at a time.

| Test | Minimum volume before a verdict |
| --- | --- |
| Cold email, deliverability or wording smoke test | 50 to 100 sends |
| Cold email, reply-rate test | ~1,500 to 2,000 sends per variant |
| Cold email, subject line or open-rate test | 100 to 500 sends per version |
| Landing page smoke test | 100 to 200 targeted visitors |
| Strict A/B test | ~10,000 visitors per variation, 300+ conversions |
| Paid ad | 1 to 3x target CPA over 48 to 72 hours |
| Cold calls | volume until one segment shows a repeatable pattern |

## Kill Rules

Write one sentence before the test starts, with four parts:

> If `<channel>` produces fewer than `<N results>` after `<M units>` by `<date>`, we stop.

- The date is the decision. Extending it after a bad result turns a test into a subscription.
- Kill on the interval, not the point estimate. A rate of 0 from 200 sends is compatible with a rate of 1.5%.
- A zero-conversion channel is killed only after 3x the units the target rate needs (rule of three: 3/n is the 95% ceiling at n attempts).
- Bounce rate above roughly 3% or any spam complaint stops the send and sends the work back to the list, not the copy.
- If the channel needs 300 sends a month and you can send 40, you are not testing it.

## Verdict Report

One block per finished test, appended to the ledger:

```
test: 2026-09-cold-email-sequence-a
channel: cold email
unit: sends
floor: 1,500 per variant (declared 2026-09-14)
observed: 1,640 / 1,610
results: 21 replies / 34 replies
verdict: SCALE b
read on: 2026-09-21
```

Four verdicts are allowed: `SCALE`, `KEEP`, `KILL`, `NOT ENOUGH DATA`. Below the floor, the last one is the only honest answer.

## What The Agent May Do

- Read the repo, the ledger, and connected analytics.
- Run the test maths and write the plan, the kill rule, and the verdict block.
- Draft email, ad, landing page, and content copy. Propose tests and offers.
- Update the ledger, append corrections, and open pull requests.

## What The Agent Must Not Do

- Send email, DMs, or posts. Spend money or change a budget.
- Publish, enable, or boost an ad campaign.
- Move a floor or a deadline on a running test.
- Rewrite or delete a ledger row after its verdict date. Append a correction instead.
- State a benchmark, a case study, or a testimonial it cannot source.

## Safety

- Never fabricate testimonials, logos, client names, or result screenshots. Bold positioning, real claims.
- Never work free: an action with no exchange (no prospect, no learning, no revenue path) gets refused, with the reasoning said out loud.
- Never recommend paid channels to a product with zero clients. The first client is won by hand.
- Tag every outbound link that points at a property you own with `utm_source`, `utm_medium`, `utm_campaign`. Never tag internal links or a URL twice.
- Do not grow this file past 200 lines. Move detail into `docs/` and link it.

## Example Tasks

- "Plan a cold email reply-rate test with a declared volume, a kill rule, and a read date."
- "Write four subject lines and tell me how to test them without polluting the reply-rate test."
- "We spent $95 against a $40 target CPA in 30 hours with one signup. Keep, re-hook, or kill?"
- "Here are the raw sends and replies. Give me the verdict block."
- "Our LinkedIn channel is 300 sends into a 1,500 send floor. What do we do this week?"
