# Record format

One Markdown file per topic: `<folder>/<slug>.md`. People read it too, so write it as a readable account of how someone's understanding grew, not a score sheet. There are no counts, scores or percentages anywhere. Keep the user's answers word for word: they are the evidence of what the user understood at that moment.

```markdown
---
topic: Bitcoin
slug: bitcoin
created: 2026-11-11
updated: 2026-11-18
---

# Bitcoin

## How deep it goes

You understand the ledger to its core: you can say why it tracks unspent outputs, not
balances, and what that buys. Proof of work you can describe, but not yet justify. You
haven't said what would break if blocks were free to make. Last time you believed
miners decide which transactions are valid. That is no longer true of your answers:
you now say every node checks the rules itself.

Next layer down: why the work has to be costly. Next step outward: where else a group
reaches agreement because cheating costs more than it pays.

## The core

Strangers who don't trust each other must agree on one history, with nobody in charge.
Making history expensive to rewrite is how bitcoin gets that agreement.

## Concept map

| # | Idea | Deepest layer shown | Notes |
|---|------|---------------------|-------|
| 1 | The ledger records unspent outputs, not balances | Core (11-18) | Mechanism (11-11) → Core (11-18) |
| 2 | Proof of work makes rewriting history expensive | Mechanism (11-11) | Can describe it; can't yet say why it must cost |
| 3 | Miners choose the order; every node checks validity | Mechanism (11-18) | Misconception (11-11) → corrected (11-18) |
| 4 | How the 21M supply limit is enforced | Not yet asked | |

## Outward connections

| Connection | Status |
|---|---|
| Byzantine generals: agreeing when some parties may lie | Not yet asked |
| Gold: scarcity that comes from the cost of producing it | Made it (11-18): "it's like gold, the cost of mining is what makes it scarce" |

## Sessions

### 2026-11-18 · session 2

**Round 1**

1. *Idea 3, rephrased · layer: core.* You run a full node on your laptop, with no mining
   hardware. A huge pool sends you a block in which one transaction has a bad signature.
   What does your laptop do, and why is that its call?
   - **Answer:** "It rejects the block. My node checks every transaction itself, so it
     doesn't matter how big the pool is."
   - **Reached:** Mechanism. Corrected since last time.
   - **Missing:** Why bitcoin is built so that every node checks: if only miners checked,
     the miners would effectively be the bank.

### 2026-11-11 · session 1

…
```

Rules:

- **Layers:** `Recall`, `Mechanism`, `Core`, `Outward`. Mark a confident wrong belief as `Misconception`. An idea not reached yet is `Not yet asked`.
- **"How deep it goes":** rewrite it in prose every time you save. It is never shown in the conversation. A separate overview skill reads it when the user asks where they stand, so make it say what they own, where they are still repeating rather than reasoning, and what the next step down and outward is.
- **Notes:** record a step only when the depth changes, in the form `Layer (MM-DD) → Layer (MM-DD)`.
- **Questions not yet answered:** write them in the session with `- **Answer:** (waiting)`, then fill them in when the user answers.
- **Sessions:** newest first. Never renumber ideas: the notes point at these numbers.
