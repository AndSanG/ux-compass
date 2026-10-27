# Severity ratings, reporting and next steps

Reference for steps 5 to 7 of the workflow. Based on Nielsen Norman Group guidance; wording and examples are original.

Contents:
- [Severity scale](#severity-scale)
- [How to decide a rating](#how-to-decide-a-rating)
- [Recording a finding](#recording-a-finding)
- [Worked example](#worked-example)
- [How many evaluators](#how-many-evaluators)
- [From findings to a usability test](#from-findings-to-a-usability-test)
- [Evaluation methods at a glance](#evaluation-methods-at-a-glance)

## Severity scale

| Rating | Name | Meaning | Action |
|---|---|---|---|
| 0 | Not a problem | You and others disagree it hurts usability | Do not report, or note as a non-issue |
| 1 | Cosmetic | Noticed, but does not slow or confuse anyone | Fix only if time allows |
| 2 | Minor | Causes small slowdowns or mild confusion; users recover easily | Low priority |
| 3 | Major | Users often fail, waste notable effort or give up on a task | High priority, fix before release |
| 4 | Catastrophic | Blocks a key task, loses data or money, or harms users | Fix immediately, before anything else |

Severity ranks the **problem**, not the heuristic. Heuristic 5 violations are not all severe; rate each on its own.

## How to decide a rating

Combine three factors, always in the context of this product and these users:

| Factor | Question | Higher severity when... |
|---|---|---|
| Frequency | How many users meet it, and on how common a task? | Many users, central task |
| Impact | How hard is it to overcome once it happens? | Fails the task, loses data, costs money, risks safety |
| Persistence | Is it a one-time hurdle or a constant drag? | Users hit it again every time, even after learning |

Context shifts the rating. A tiny delay in a game may be a 1; the same delay confirming a bank transfer is a 3. A missing Undo on a draft email may be a 2; on bulk deletion of customer records it is a 4.

Rules of thumb:
- Frequent plus high impact plus persistent leans 4.
- Rare plus easily recovered plus one-time leans 1 or 2.
- If you hesitate between two ratings, choose the higher one only when data loss, money or safety is involved; otherwise explain the doubt in the reason column.
- Rate independently first, then compare across findings for consistency (all your 3s should feel similar in weight).
- When several evaluators rate, average or discuss differences; a spread of two or more points signals a missing assumption.

## Recording a finding

One row per problem:

| Field | Content |
|---|---|
| ID | F1, F2, ... |
| Where | Screen, step or element; add a screenshot reference if available |
| Problem | What happens and what the user experiences; no solution here |
| Heuristic(s) | Number and name |
| Severity | 0 to 4, with the reason (frequency, impact, persistence) |
| Suggested fix | Concrete, testable change |
| Pattern | The design pattern that supports the fix |
| Evidence | Observed directly, inferred from screenshots, or reported by users |

Write problems from the user's point of view: "Users cannot tell whether a payment went through" rather than "The button lacks a loading state".

## Worked example

Context: a payments screen in a small-business app, assumed users are shopkeepers who pay suppliers a few times a week.

| # | Where | Problem | Heuristic | Severity and why | Suggested fix | Pattern |
|---|---|---|---|---|---|---|
| F1 | Pay screen, "Pay" button | Tapping "Pay" gives no visible response for several seconds, so users tap again | 1 Visibility of system status; 5 Error prevention | 4: duplicate payments cost money; happens on every payment | Disable the button on tap, show progress, then a receipt with amount and time | Safe Exploration |
| F2 | Pay screen, amount field | Error shows only a red border, no text | 9 Error recovery | 3: users cannot tell what to fix; frequent on first use; colorblind users miss it | Add inline text: "Amount can't be higher than your balance" | Proximity |
| F3 | Supplier list | Suppliers sorted by creation date, not by recent payment | 7 Flexibility and efficiency | 2: extra scrolling each time, but a search exists | Show recent suppliers first, keep search | Streamlined Repetition |
| F4 | Header | Logo and menu icon use slightly different grays on two screens | 4 Consistency | 1: nobody is slowed down | Use the shared color token | Visual Framework |

What works well: the supplier cards share one template, so users learn one card and understand all (4, Grid of Equals logic); the pay confirmation summary shows supplier and amount before charging (5).

Top fixes: F1 first (catastrophic), F2 second (major, frequent).

## How many evaluators

- One evaluator finds only a fraction of the problems; different people find different ones.
- Three to five independent evaluators together find most of them. Have each evaluate alone first, then merge the lists and rate together.
- If only you (or one agent) can evaluate, say so in the limits and recommend a second review or a short user test.

## From findings to a usability test

Inspection tells you what is likely wrong; a test with real users confirms and finds what experts miss.

- Use **5 users** per round for qualitative findings, and test small and often, fixing between rounds, rather than one large test. It is not meant for statistics.
- Recruit people who match the audience; give representative tasks ("Pay the invoice for your supplier Ruiz"), not instructions about the interface.
- Each person tests **individually**. Observe without helping; note where they hesitate, err or ask questions; encourage thinking aloud.
- Do not use focus groups to evaluate a design: people report what they believe they would do, not what they do.
- Turn the top severity 3 and 4 findings into test tasks, and add a success criterion for each (for example: "4 of 5 complete the payment without asking for help").

## Evaluation methods at a glance

| Family | Examples | Who | Strength | Limit |
|---|---|---|---|---|
| Inspection | Heuristic evaluation (Nielsen and Molich), cognitive walkthrough (Polson et al.) | Experts, no users | Cheap, quick, early | Finds likely problems, not real performance |
| Critique | Design review, peer feedback | Colleagues, experts | Fast opinions | Subjective, uneven |
| Laboratory | Moderated usability test, controlled study | Users in a controlled setting | Real behavior, comparable measures | Cost and artificial context |
| Field | Observation, diary studies, analytics | Users in real contexts | Real context | Hard to control, slower |

A sound sequence: inspect early to clear obvious problems, then test with users, then measure with analytics once the product ships.
