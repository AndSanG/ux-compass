# Design rationale template

Use this for step 4 of the workflow. A rationale makes a design reviewable: anyone can challenge a decision by challenging the user need or the principle behind it, not by trading opinions.

## Template

```markdown
## User frame
- Audience:
- Goal (after asking why):
- Skill and motivation:
- Context of use (device, place, time pressure):
- Assumptions to validate:

## Patterns in play
| Pattern | Why it applies here | Design move |
|---|---|---|

## Layout
- Primary element:
- Secondary:
- Tertiary:
- Page-level pattern:
- Chunking pattern(s):
- Narrow-screen behavior:

## Decisions
| # | Decision | User need or goal | Principle or pattern | Alternative rejected, and why |
|---|---|---|---|---|

## Open questions and tests
- What we assumed and how we will check it:
- What to watch for in the first usability test:
```

Rules for the Decisions table:
- One row per decision someone could reasonably question.
- "User need" quotes the user frame, not the stakeholder's wish.
- "Principle or pattern" names a behavioral pattern, a layout pattern, a Gestalt principle, or a hierarchy tool.
- Always fill "Alternative rejected": it shows the decision was a choice.

## Worked example: prescription refill on a pharmacy app

### User frame
- **Audience:** adults managing recurring medication, often for themselves and an older relative; many are occasional app users. Mostly on phones, often while doing something else.
- **Goal:** never run out of a medicine. Refilling is the means; the deeper goal is continuity of treatment without a trip or a phone call.
- **Skill and motivation:** low to medium; they open the app only when a refill is due and want it done in under a minute.
- **Context:** short sessions, interruptions likely (Microbreaks, Changes in Midstream).
- **Assumptions to validate:** most refills are repeats of the same order; managing a relative's prescriptions is common.

### Patterns in play
| Pattern | Why it applies here | Design move |
|---|---|---|
| Instant Gratification | Users open the app with one job in mind | The home screen shows medicines due soon with a one-tap "Refill" each |
| Streamlined Repetition | Most refills repeat the previous order | "Refill all due" in one action, with the last delivery and payment options preselected |
| Deferred Choices | Delivery details rarely change | Reuse the previous choices; changing them is optional and comes later in the flow |
| Safe Exploration | Fear of ordering the wrong item or quantity | Clear summary before confirming, plus cancellation within a time window |
| Spatial Memory | People return every few weeks | The refill list and button stay in the same spot on every visit |

### Layout
- **Primary:** the list of medicines due soon, each with its Refill button.
- **Secondary:** a "Refill all due" action and the profile switcher (self or relative).
- **Tertiary:** order history, pharmacy hours, help.
- **Page-level pattern:** Center Stage (the due list) within the app's Visual Framework.
- **Chunking:** Titled Sections "Due soon" and "Other prescriptions"; history in a separate tab of the main navigation.
- **Narrow screen:** the due list starts right under the header; "Refill all due" stays fixed at the bottom within thumb reach.

### Decisions
| # | Decision | User need or goal | Principle or pattern | Alternative rejected, and why |
|---|---|---|---|---|
| 1 | Due list is the first thing on the home screen | Finish the refill in under a minute | Center Stage, Instant Gratification | A promotional banner at the top: competes for the first focal point with an action users did not come for |
| 2 | One-tap refill reusing last delivery and payment | Most orders repeat | Streamlined Repetition, Deferred Choices | A full checkout form every time: adds effort with no new information |
| 3 | Profile switcher next to the screen title | Caregivers order for others | Proximity (who this list belongs to) | Hiding it in settings: users would refill for the wrong person |
| 4 | Confirmation summary plus a cancellation window | Fear of mistakes with medication | Safe Exploration | A modal "Are you sure?" dialog: becomes a reflex click (Habituation) |
| 5 | Each medicine card uses the same template | Compare dose, quantity and due date quickly | Similarity, Grid of Equals logic for list items | Varying card designs by medicine type: breaks scanning rhythm |

### Open questions and tests
- Check with 5 users that "Refill all due" is not mistaken for refilling every prescription.
- Watch whether caregivers notice the profile switcher without help.
