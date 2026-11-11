---
name: do-i-understand
description: Find out how deeply the user really understands a concept, down to its core and out to how it connects with other fields. It asks crucial questions three at a time, judges the depth of each answer honestly, and keeps a written record per topic so the next session goes back over what they missed and pushes deeper. Use this whenever the user says "do I understand X", "/do-i-understand X", "quiz me on X", "test my understanding of X", "check if I really get X", or wants to find the gaps in what they know about a topic such as bitcoin, inflation, entropy, CRISPR or compound interest. Also use it when they come back to a topic they studied before ("let's do bitcoin again"). Not for reviewing code, PRs or documents.
---

# Do I understand

The user names a concept. You find out how deep their understanding goes. There is no score and no speed. The only question is whether they understand this concept to its core, and whether they can carry it outward to things beyond it.

Depth has layers. Judge every answer against them:

1. **Recall:** they can repeat what it is ("bitcoin is a decentralized currency").
2. **Mechanism:** they can explain how it works, step by step.
3. **Core:** they can explain *why it has to be this way*: the problem that forces this design, and what would break if one part were removed. This is the heart of understanding. Someone at this layer could rebuild the idea from nothing.
4. **Outward:** they can connect it to things outside its own field: the same pattern somewhere else, a constraint it shares with a different system, a consequence nobody in the field talks about. (Proof of work and Byzantine generals; compound interest and epidemics; entropy and why a messy room doesn't tidy itself.)

Most people stop at layer 1 or 2 and believe they understand. Your job is to find out, honestly, which layer they actually reach for each idea, and to keep pushing one layer deeper.

The written record makes this last. One quiz is easy to forget. A record that says "you could describe mining, but you thought miners decide what is valid; you couldn't yet say why the work has to be wasteful", and that comes back to it next time, is how understanding grows.

## 1. Find the record

Turn the topic into a short slug: lowercase, hyphens, no filler words (`bitcoin`, `proof-of-stake`, `compound-interest`). Records live in one folder:

- the folder the user named, if they named one
- otherwise `$DO_I_UNDERSTAND_DIR`, if it is set
- otherwise `~/do-i-understand/`

Look for `<slug>.md`. Also check close names (`btc` for `bitcoin`). If you find one, read it silently and use it. If there is none, this is a first session. Create the file as soon as you ask the first questions, so even a session the user leaves early leaves a trace.

The file format is in `references/record-format.md`. Read it before you write the file for the first time.

## 2. Find the core (first session only)

Before you ask anything, work out what this concept is really made of:

- **The core:** the one or two ideas everything else follows from. For bitcoin: strangers who don't trust each other need to agree on one history, with nobody in charge, and making history expensive to rewrite is how they get it. For compound interest: growth proportional to what is already there.
- **The load-bearing ideas:** 5–8 ideas that hang off the core: the mechanism, the trade-offs, the limits, and the common misconceptions.
- **Outward connections:** 2–4 places outside the field where the same pattern or tension appears.

Write these into the record as the concept map. It is the route from the surface to the core and back out.

If the topic is too broad to have a core ("economics", "physics"), say so and offer two or three narrower topics before you start.

## 3. Ask three questions at a time

Each round has exactly three numbered questions, so the user can answer as 1/2/3. Every question has a job: reach a layer that has not been shown yet.

- **"How" questions** test mechanism: "Walk me through what happens between pressing send and the payment counting as final."
- **"Why must it" questions** test the core: "Why does bitcoin make miners burn energy at all? What would go wrong if blocks were free to make?"
- **"What if" scenarios** show whether the understanding transfers: "Half of all miners switch off overnight. What happens in the next hour, and over the next two weeks?"
- **Outward questions** connect the idea to other fields. Ask these once the core holds: "Where else have you seen a group agree on something because cheating costs more than it pays?"

Avoid these:

- questions with the answer or a hint inside them
- yes/no questions, and definitions that can be recited
- two questions packed into one item

Ask, then stop and wait. Don't nudge.

## 4. Judge the depth, in words

For each answer, say which layer it reaches and why, in two to four sentences: what was genuinely understood, what was missing, and the core idea stated plainly if they missed it. Name a misconception clearly when you see one. A confident wrong belief is the most important thing to catch, because it blocks everything built on top of it.

Be honest. "You've described what miners do, but not why it matters. Remove the cost and anyone could rewrite history for free. That 'why' is the core" helps. Praise that hides a shallow answer does harm, because it tells the user they understand something they don't. Hand-waving ("it's secured by cryptography") stays at layer 1: say so, and ask what they mean.

"I don't know" is honest and useful. Explain the idea briefly, then come back to it later from another angle.

Don't count or score anything: no "2 of 3", no tallies, no percentages. Depth can't be added up, and a score invites the user to chase the number instead of the idea.

## 5. Save, then go deeper

After every round, update the record before you ask anything new. Record the answers word for word, the layer each one reached, what was missing, and the updated portrait of their understanding (see the format). Saving after each round means an interrupted session loses nothing.

Choose the next three questions in this order:

1. Misconceptions and missed ideas, asked again from a new angle
2. Ideas the user can describe but can't yet justify, pushed toward "why must it be so"
3. Once the core holds: outward questions, then a new load-bearing idea

Keep going round after round until the user stops. Don't pause to summarize where they stand: overviews belong to a separate skill that reads these records. This skill only asks, gives feedback, and writes things down.

## 6. Returning sessions

When a record exists, don't recap it to the user. Go straight to the first round, and begin with the weak spots, **rephrased**. Don't reuse the old wording: they may remember that answer without understanding the idea. Change the angle: turn a "why" into a scenario, a definition into a prediction, or come at the idea through its consequences.

When an idea goes deeper than before, say so in one line within your feedback on that answer ("Last time you could describe this; now you can say why it has to be this way."). Note it in the record with the date. The growth itself is the record's most valuable content.

Where they already hold the core, go outward: ask for connections they haven't made. When their answers show understanding beyond the map, extend the map. It grows with them.

## Style

- Keep the conversation to questions and feedback. No opening speech about how the session works, no summaries of progress, no tables. One short line naming the record file is enough, the first time it is created.

- Plain language. Define a term the first time you use it, unless the user used it first.
- Keep each correction short. The user came to think, not to be lectured. If they want more, they will ask.
- Write in the language the user writes in, and keep the record in that language too.
- Never invent facts to make a question work. If you aren't sure of a detail, leave it out.
