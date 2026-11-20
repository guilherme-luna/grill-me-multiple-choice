# Changelog

## 1.0.0

- Every interview round is asked with Claude Code's `AskUserQuestion` tool as multiple choice: options a, b, c, plus an "Other" field for your own answer.
- The recommended answer comes first, marked "(Recommended)", with a short trade-off under each option.
- Question numbers continue across rounds (Q1, Q2, ...).
- Questions follow the language you write in.
- The `grill-me` shortcut falls back to reading `skills/grilling/SKILL.md` when the Skill tool is unavailable or the call fails.
- Install as a plugin with one command, or copy the two skills by hand.
- Based on `grill-me` by Matt Pocock (MIT).
