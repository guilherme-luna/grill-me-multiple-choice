---
name: grilling
description: Grill the user relentlessly about a plan, decision, or idea. Use when the user wants to stress-test their thinking, or uses any 'grill' trigger phrases.
---

Interview the user relentlessly until you reach a shared understanding. Map this as a **design tree**: every decision branches into the decisions that hang off it.

Work the tree in **rounds**. The **frontier** is every decision whose prerequisites are already settled: the questions you can ask _now_ without guessing at answers you haven't heard yet. Ask the whole frontier in one round: number each question and give your recommended answer. Then wait for the user's answers before the next round.

**Always ask each round with the AskUserQuestion tool as multiple choice — never as plain text.** Rules:

- Write questions and options in the user's language (Portuguese if they write in Portuguese).
- Number questions across the whole session (Q1, Q2, … continuing between rounds) and put the number at the start of the question text, e.g. "Q5 – ...". Make each question self-contained (name the project/thing it is about), since the user may see only the dialog.
- Give 2–3 options (a, b, c). The tool adds an "Other" field automatically, which is the user's free-text option (d) — never add your own "Other" option.
- Put your recommended answer as the **first** option with "(Recomendado)" / "(Recommended)" at the end of its label. Use the option description to explain the trade-off.
- The tool takes at most 4 questions per call. If the frontier has more than 4, split it into several consecutive calls within the same round.
- Read free-text answers carefully: they may add conditions or new decisions that open new branches of the tree.

Before a round, you may write one short line of text with relevant facts you found (e.g. "verified: Node 22 installed"), but the questions themselves go only in the tool.

Each round the user answers reshapes the tree: settled decisions push the frontier outward and unblock questions that depended on them. Recompute the frontier and ask the next round. A question whose answer depends on another question still open in this round belongs to a _later_ round, not this one.

Finding _facts_ is your job, never the user's. When a frontier question needs a fact from the environment (filesystem, tools, etc.), dispatch a sub-agent with a fresh context window to find it; don't ask the user for anything you could look up yourself. Don't block on it: a running exploration is an unsettled prerequisite, so only the questions downstream of it wait for the sub-agent to report; ask the rest of the frontier now. The _decisions_ are the user's: put each to them and wait.

The session is done when the frontier is empty: every branch of the design tree visited, nothing left silently assumed. Do not act on it until the user confirms you have reached a shared understanding.
