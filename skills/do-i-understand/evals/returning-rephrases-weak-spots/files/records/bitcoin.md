---
topic: Bitcoin
slug: bitcoin
created: 2026-11-04
updated: 2026-11-04
---

# Bitcoin

## How deep it goes

You understand the ledger to its core: you can explain why it tracks unspent outputs rather than balances. Everything else is still on the surface. You think old blocks are hard to change because they are "encrypted"; nothing is encrypted. You believe miners decide which transactions are valid, and that the supply limit is held by "the company behind it". Neither is true, and the second one hides the core: nobody is in charge.

Next layer down: who actually enforces the rules, and why rewriting history has to be costly.

## The core

Strangers who don't trust each other must agree on one history, with nobody in charge. Making history expensive to rewrite is how bitcoin gets that agreement.

## Concept map

| # | Idea | Deepest layer shown | Notes |
|---|------|---------------------|-------|
| 1 | The ledger records unspent outputs, not balances | Core (11-04) | |
| 2 | Proof of work makes rewriting history expensive | Recall (11-04) | Thinks blocks are "encrypted" |
| 3 | Miners choose the order; every node checks validity | Misconception (11-04) | Thinks miners decide validity and "vote" |
| 4 | How the 21M supply limit is enforced | Misconception (11-04) | Thinks a company stops "printing" |
| 5 | What a private key proves | Not yet asked | |
| 6 | Why confirmations matter | Not yet asked | |

## Outward connections

| Connection | Status |
|---|---|
| Byzantine generals: agreeing when some parties may lie | Not yet asked |
| Gold: scarcity that comes from the cost of producing it | Not yet asked |

## Sessions

### 2026-11-04 · session 1

**Round 1**

1. *Idea 1 · layer: core.* Alice has 0.7 BTC from one payment and 0.5 BTC from another. She sends Bob 1 BTC. What does that transaction consume and create?
   - **Answer:** "It spends both old outputs and creates one for Bob and one change output back to Alice, minus the fee. There are no balances, just outputs that are spent or not, so you can check a payment without replaying everyone's account."
   - **Reached:** Core.
   - **Missing:** Nothing at this level.

2. *Idea 3 · layer: mechanism.* A miner wants to include a transaction that spends coins it doesn't own. What stops it?
   - **Answer:** "The miner decides if it's valid, and the other miners vote on it."
   - **Reached:** Misconception.
   - **Missing:** Every full node checks every transaction against the rules on its own. A block with an invalid transaction is rejected however much work went into it. Miners only choose which valid transactions go in, and in what order.

3. *Idea 4 · layer: mechanism.* Why can there never be more than 21 million bitcoin?
   - **Answer:** "I think the company behind it stops printing them?"
   - **Reached:** Misconception.
   - **Missing:** There is no company. The block reward is part of the rules every node enforces, and it halves every 210,000 blocks. A block that pays itself more is invalid, so the total supply approaches 21 million and never passes it.

**Round 2**

1. *Idea 2 · layer: core.* Why would rewriting a block from a week ago be so hard?
   - **Answer:** "Because it's encrypted and you'd need to break the encryption."
   - **Reached:** Recall.
   - **Missing:** Nothing is encrypted. Each block commits to the one before it, so changing an old block means redoing its proof of work and that of every block after it, faster than the rest of the network adds new ones.
