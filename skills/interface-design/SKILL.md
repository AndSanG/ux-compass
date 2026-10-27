---
name: interface-design
description: Guides UI/UX design decisions for screens, apps, web pages, dashboards, forms and prototypes (Figma, wireframes, mockups), starting from the people who will use them and ending in a justified screen layout. Use when designing or redesigning an interface, deciding what goes where on a screen, choosing between layouts (single focus area, card grid, tabs, accordion, side panels), turning personas or user goals into a UI, or explaining why a design choice is right. Not for auditing an existing interface against usability heuristics.
---

# Interface design

Make interface decisions that start from the people who will use the product and end in a layout where every choice can be traced back to a user need.

Two rules drive everything below:

1. **People before pixels.** No layout until you can say who the users are, what outcome they want, and how much effort they will invest. The interface is only a means to their end.
2. **Every decision has a reason.** Each placement, grouping or pattern choice names the user need it serves and the principle behind it. "It looks clean" is not a reason.

## When to use

- Designing a new screen, flow or app, or redesigning an existing one.
- Questions like "where should this go?", "tabs or accordion?", "how do I make this stand out?", "this page feels cluttered".
- Turning research, personas or requirements into a first layout.
- Reviewing your own design proposal before building it.

Not for: scoring an existing product against heuristics (use a usability evaluation method instead), brand identity or illustration work, or framework-specific code questions. The rationale produced here can still feed implementation.

## Workflow

### 1. Frame the people

Read `references/designing-for-people.md` when the request involves a new product, an unclear audience, or onboarding and first-use flows.

Write a short **user frame** before proposing anything:

| Item | Question to answer |
|---|---|
| Audience | Who uses it, where, on which device, in what situation? |
| Goal | What outcome do they actually want? Ask "why?" repeatedly: filling a form or opening a menu is never the goal. |
| Goal type | Find, learn, complete a transaction, control or monitor, create, communicate, or be entertained? |
| Tasks | Which steps lead to the goal, and how often are they repeated? |
| Vocabulary | Which words do *they* use for these things? |
| Skill and motivation | Occasional, intermediate or expert? How much learning will they tolerate? |
| Attitudes | Feelings, expectations and social context that could make or break adoption. |
| Openness | Should the interface guide them step by step, or open many tools at once? |

If information is missing, do not invent it silently. Either ask, or list the assumptions clearly labeled as such, together with the cheapest research that would confirm them (a few interviews, watching someone do the task, a short survey). "Everyone" is never an audience.

### 2. Pick the behavioral patterns in play

People behave in predictable ways around software. Choose the 3 to 5 patterns that most shape *this* design and state the concrete design move each one implies. Quick map (details and more patterns in the reference):

| If the users... | Pattern | Design move |
|---|---|---|
| are new or unsure and need to try things | Safe Exploration | Undo, reversible actions, predictable Back, no punishing side effects |
| decide in seconds whether the product is worth it | Instant Gratification | First meaningful success within seconds; no sign-up or tutorial wall before value |
| scan and click the first plausible option | Satisficing | Clear call to action, short plain labels, layout that signals meaning, easy way back |
| switch goals halfway through | Changes in Midstream | Links to related tasks, save progress, let them leave and resume |
| hit questions they cannot or will not answer yet | Deferred Choices | Few required fields, sensible defaults, "you can change this later" |
| build or compose something | Incremental Construction | Instant preview, fast save and edit loop, cheap small changes |
| repeat actions until they become reflexes | Habituation | Same gesture, same result everywhere; avoid confirmation dialogs that get clicked blindly |
| use the product in short idle moments | Microbreaks | Fast launch, stay signed in, freshest content first, resume where they left off |
| find things by where they were | Spatial Memory | Keep controls and menu items in stable places; do not rearrange for them |
| leave things around as reminders | Prospective Memory | Keep drafts, recent items and user-placed markers; never auto-clean their stuff |
| do the same operation many times | Streamlined Repetition | Batch actions, "apply to all", templates, shortcuts |
| cannot or prefer not to use a pointer | Keyboard Only | Full keyboard path, logical focus order, default action on Enter |
| care what others think or do | Social Proof and Collaboration | Reviews, activity of known people, sharing and commenting on objects |

### 3. Lay out the screen

Read `references/screen-layout.md` for the details of each step and for the layout patterns.

1. **Name the one primary thing** on the screen (content or action). Rank everything else as secondary or tertiary. If two things compete for first place, resolve it with the user frame, not by making both loud.
2. **Choose the page-level pattern.** Inside a shared **Visual Framework** (consistent regions, type, color, spacing across screens), use **Center Stage** when one document, task or object is the point of the screen, or a **Grid of Equals** when many similar items are offered as peers.
3. **Group and chunk.** Use proximity and similarity so related things read as one unit. If there is more content than fits comfortably, pick a chunking pattern with the decision guide in the reference (Titled Sections, Module Tabs, Accordion, Collapsible Panels, Movable Panels).
4. **Express importance** with size, position, spacing, contrast and background, and repetition. Align everything to a grid.
5. **Plan the visual flow.** Decide the order the eye should follow, keep focal points few, and place each call to action right after the content that motivates it.
6. **Use time and interaction** when space runs out: scrolling, enabling controls only when they become relevant, revealing detail on demand.
7. **Assign regions** (header, navigation, main content, panels, footer) and check the narrow-screen version: what moves, what collapses, what stays above the fold.

### 4. Write the rationale

Use `references/design-rationale-template.md`. One row per significant decision: decision, user need, principle or pattern, alternative rejected and why. This is what makes the design defensible to a team, a client or a reviewer.

## Output

For a design request, deliver in this order:

1. **User frame** (short, assumptions marked).
2. **Patterns in play** and the design move each one implies.
3. **Layout**: regions and hierarchy ranks, as an ASCII wireframe, HTML, or step-by-step instructions for the user's tool (Figma, etc.), whichever the user is working in.
4. **Rationale table.**
5. **Open questions and what to test** with real users.

For a narrow question ("where do the filters go?"), answer in a few lines, but still name the user need and the principle behind the answer.

Answer in the user's language. Pattern names may stay in English, with a short gloss the first time.

## Checklist before delivering

- [ ] The user frame comes before the layout, and assumptions are labeled.
- [ ] Exactly one element is primary, and it matches the users' main goal.
- [ ] The first useful outcome is reachable fast, with nothing mandatory blocking it.
- [ ] Every risky action can be undone or safely abandoned.
- [ ] Labels use the users' words and are short enough to scan.
- [ ] Related items are grouped by proximity and similarity; unrelated items are visibly separated.
- [ ] The eye path follows the order of the task; there are few focal points and no competing calls to action.
- [ ] Recurring elements stay in the same place across screens (Visual Framework, spatial memory).
- [ ] Hidden content (tabs, accordions, panels) is truly secondary, and its labels predict what is inside.
- [ ] Repetitive work has a shortcut or batch option, and the main path works with a keyboard.
- [ ] The narrow-screen version keeps the primary element first.
- [ ] Every row in the rationale cites a user need, not taste.

## Source

The concepts and pattern names come from J. Tidwell, C. Brewer and A. Valencia, *Designing Interfaces*, 3rd ed. (O'Reilly, 2020), chapter 1 "Designing for People" and chapter 4 "Layout of Screen Elements". The explanations and examples in this skill are original summaries written for decision-making; read the book for the full treatment.
