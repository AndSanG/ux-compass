---
name: interface-evaluation
description: Evaluates an existing interface (live product, screenshots, prototype, wireframe) for usability problems using heuristic evaluation with Nielsen's 10 heuristics, rates each problem's severity, and proposes prioritized fixes tied to design patterns. Use when asked to review, audit, critique or test an interface, find usability issues, check a design against heuristics, prioritize what to fix first, or plan a usability test. Not for creating a new design from scratch.
---

# Interface evaluation

Find the usability problems in an existing interface, rank them, and say what to change. Evaluation answers "what is wrong and how bad is it"; design answers "what should it be". Fixes are handed to the `interface-design` skill's patterns when it is available.

## Be honest about what this method is

Heuristic evaluation is an **inspection** method: an expert reviews the interface against general principles, without users. It is cheap and fast, and it finds *likely* problems. It does not measure how well real people perform, and it cannot replace a usability test. State this limit in every report.

## When to use

- "Review this screen / flow / prototype."
- "Why is this confusing?", "what would you fix first?"
- Comparing a design against competitors or an earlier version.
- Preparing the tasks and criteria for a usability test.

Not for: creating the layout from scratch (use `interface-design`), accessibility conformance audits (WCAG checks are a separate, stricter process), or visual-brand critique.

## Choosing the method

| Situation | Method | Notes |
|---|---|---|
| No users available, need quick findings | Heuristic evaluation (this skill) | Several independent evaluators find far more than one |
| Need to know if first-time users can complete a task | Cognitive walkthrough, then a usability test | Walk each step asking if the user would know what to do and see progress |
| Need real behavior and evidence | Usability test with users | See `references/severity-and-reporting.md` |
| Need numbers (time, success rate, satisfaction) | Quantitative study | Beyond this skill |

## Workflow

1. **Set the scope.** Which product, which screens or flows, which users, which tasks, on which device. Evaluating "the whole app" is too vague; evaluate representative tasks. If the user does not say, state the scope you assumed.
2. **Know the users first.** Problems only count relative to the people and goals they affect. Use the user frame if one exists; otherwise write two lines (who, what they want) and mark them as assumptions.
3. **Walk the tasks.** Go through each task step by step at least twice: once to get the overall flow, once to inspect each screen against the heuristics. Work from what you can actually see; never invent screens or behavior. If you only have screenshots, say what you could not check (states, errors, loading, responsive behavior).
4. **Log each problem** the moment you see it, against one or more of the 10 heuristics (`references/heuristics.md`). Describe the problem, not the solution.
5. **Rate severity** for each problem (`references/severity-and-reporting.md`): frequency, impact, persistence, in the context of the product.
6. **Propose a fix** per problem, concrete and testable, with the design pattern that supports it (map in `references/heuristics.md`).
7. **Prioritize and report** in the format below. Also list what works well, so the team does not break it.

If several evaluators are available (people or agents), have each work alone first, then merge. Independent reviews avoid bias and surface different problems.

## Output format

Deliver in this order:

1. **Scope and assumptions**: what was reviewed, how (screenshots, live, prototype), users and tasks assumed, and what could not be checked.
2. **Summary**: count of problems by severity, and the top 3 to fix first.
3. **Findings table**, sorted by severity (highest first):

| # | Where | Problem | Heuristic | Severity (0-4) and why | Suggested fix | Pattern |
|---|---|---|---|---|---|---|

4. **What works well** (2 to 4 items, tied to heuristics).
5. **Limits and next step**: what a usability test with 5 users should check first.

Keep each cell specific. "Bad navigation" is not a finding; "The Back arrow on step 3 returns to the home screen and loses the form data" is.

Answer in the user's language. Heuristic names may stay in English, with a short gloss the first time.

## Rules for good findings

- **One problem per row.** If it breaks two heuristics, list both heuristics in one row; if it is two problems, make two rows.
- **Evidence over taste.** Point to the exact element and the effect on the user's task. "I don't like the color" is not a finding; "light gray text on white has low contrast and the price is hard to read" is.
- **Describe, then explain.** What happens, then why it matters for these users.
- **Severity needs a reason**, always. The same flaw can be minor in a game and critical in a banking app.
- **No false precision.** Heuristics are general principles, not a checklist to tick; the same issue can be justified under more than one.
- **Do not penalize conventions that match the audience** just because you would do it differently.
- **Praise what works**, briefly. It protects good decisions from being "fixed".

## Checklist before delivering

- [ ] Scope, users and tasks stated; limits of the evidence stated.
- [ ] Every finding names the screen or element, the heuristic(s), a severity with its reason, and a fix.
- [ ] No finding describes a solution as if it were the problem ("needs a dropdown").
- [ ] Severity ratings are consistent across findings (compare the 3s and the 4s).
- [ ] The top fixes address the most severe problems on the most frequent tasks.
- [ ] Positives listed.
- [ ] The report says it is an expert inspection and recommends user testing.

## Source

Heuristics and severity ratings: J. Nielsen and R. Molich, heuristic evaluation (1990); J. Nielsen, "10 Usability Heuristics for User Interface Design" and "Severity Ratings for Usability Problems", Nielsen Norman Group (nngroup.com). The wording, tables and examples here are original summaries. Pattern names in the mapping come from J. Tidwell, C. Brewer and A. Valencia, *Designing Interfaces*, 3rd ed. (O'Reilly, 2020).
