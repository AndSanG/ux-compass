# Designing for people

Reference for step 1 and step 2 of the workflow. Concepts from *Designing Interfaces* (3rd ed.), chapter 1; page numbers point to that edition. Explanations and examples are original.

Contents:
- [Four foundations](#four-foundations)
- [Context](#context)
- [Goals](#goals)
- [Research](#research)
- [Behavioral patterns](#behavioral-patterns)
- [Choosing patterns for a brief](#choosing-patterns-for-a-brief)

## Four foundations

Understanding people for design rests on four areas (p. 2):

| Area | Question | What you produce |
|---|---|---|
| Context | Who is the audience? | Audience description, skill level, openness of the interface |
| Goals | What are they trying to achieve? | Goal statement per user group, task breakdown |
| Research | How do we know? | Evidence from real users, or labeled assumptions plus a plan to check them |
| Patterns | How do people think and behave around software? | The behavioral patterns this design must support |

How much effort each area gets depends on the project, but skipping one entirely is a risk you should name.

## Context

**You are not the user** (p. 2). Your own habits, vocabulary and comfort with technology are evidence about one person: you.

**An interaction is a conversation** (pp. 2-3). The person asks, the system answers, back and forth. For that to work, the interface has to:
- show that it received the input,
- show that it is working,
- show the result clearly,
- where possible, suggest a sensible next step.

Design questions that follow: what are the user's intentions, what words, icons and gestures do they expect, and how does the interface set the right expectations?

**Match the conversation to the listener** (pp. 3-4):
- Use domain words at the level users know; offer a way to learn the unfamiliar ones.
- People with little technical confidence should not face unusual controls or conventions.
- Low interest means low tolerance: ask for little effort, give value quickly.

**Decide how open the interface is** (p. 4). A spectrum runs from fully guided (step-by-step flows with Next and Back only) to fully open (a workspace exposing hundreds of tools at once). Too closed and capable users feel trapped; too open and newcomers freeze. Pick the point on the spectrum from the user frame, not from what the team finds elegant.

**Skill level** (pp. 4-5). Ask honestly whether most users will become experts or stay occasional:

| Users are mostly... | Design leans toward | Typical products |
|---|---|---|
| Occasional or one-time | Few features, explanation along the way, guided flows, no assumed conventions | Self-service kiosks, checkout pages, setup assistants |
| In the middle (most products) | Easy first steps plus efficient paths for frequent users | Mail, messaging, presentation tools |
| Daily, expert | Efficiency over learnability, dense workspaces, shortcuts, lists and documents at the center | Professional editors, IDEs, admin consoles |

Experts tolerate a steep learning curve but grow intolerant of small, repeated annoyances. Occasional users tolerate rough edges but will not invest in learning.

## Goals

**The interface is a means to an end** (p. 6). Common goal types: find something, learn something, complete a transaction, control or monitor something, create something, communicate with people, be entertained. Each type has well-known supporting idioms; name the type before designing.

**Ask why, then ask again** (p. 6). Clients and users describe features and solutions. Keep asking "why?" until you reach a need beyond the immediate screen. Example: "we need an export button" → why? → "to send the monthly report to the accountant" → why? → "the accountant needs the totals by category". Perhaps a scheduled email with totals solves the real problem better than any button.

**Solve the right problem, then solve it right** (pp. 6-7). If a step can be removed (the form, the confirmation, the extra screen), removing it beats designing it beautifully.

**Goals shift and users are plural** (p. 7). One visit can mix goals (someone comes to buy and ends up browsing tutorials), and a site can serve several audiences at once. Do not model a single faceless "user" walking one happy path.

**Softer factors matter** (p. 8): what people expect, how they feel at first sight, what they like, who is around them, and what they believe in. The detail that makes a product feel right for its audience often hides here.

## Research

Empirical contact with users is the reliable source for context and goals (pp. 8-11). Learn:
- their goals,
- the tasks they perform to reach them,
- the words they use,
- their skill with similar software,
- their attitudes toward this kind of product.

Methods (choose by budget and risk):

| Method | Good for | Watch out for |
|---|---|---|
| Direct observation and interviews, ideally where the product is used | Goals, tasks, vocabulary, surprises you did not know to ask about | Small samples; ask "why" more than once |
| Case studies | Depth on a few representative or extreme users, long-term use, custom software | Not representative on their own |
| Surveys | Numbers across many users | You only learn what you ask; question and sample design is a skill |
| Personas | Turning research into a few fictional but grounded users to check decisions against ("would she really do this?") | A persona without research behind it is a guess with a name |

**Design research is not market research** (p. 10). Market segments describe who *buys* (demographics); design audiences describe who *uses* (goals and behavior). Focus groups can be dominated by one or two voices.

People cannot always explain what they need, and self-reports are biased. Even so, a handful of informal conversations beats no contact at all (p. 11).

## Behavioral patterns

These describe how people behave, not interface components (p. 11). Support them and users reach their goals more easily. Each entry: what it means, signals that it matters in your brief, design moves, a common mistake, and an example.

### Safe Exploration (p. 12)

People learn more and feel better when trying something has no painful consequence. Even small annoyances (losing typed text, an unexpected sound, a pop-up to dismiss) discourage exploring.

- **Signals:** new users, rich feature sets, anything with settings, filters or editing.
- **Moves:** undo (several levels where it makes sense), reversible actions, previews before committing, a Back that always behaves the same, no surprise windows.
- **Mistake:** a custom "back" control that behaves differently from the platform Back.
- **Example:** in a budgeting app, changing a category's color or name can be undone from a toast message for a few seconds, so users try options freely.
- Related heuristics for later evaluation: visibility of system status, match with the real world, user control and freedom.

### Instant Gratification (p. 13)

An early success makes people stay, and makes them more confident in the product and in themselves.

- **Signals:** consumer apps, trials, onboarding, low motivation.
- **Moves:** predict the first thing a newcomer wants and make it effortless; put an obvious entry point on the first screen; give value before asking for something (email, payment, permissions).
- **Mistake:** sign-up walls, long tutorials, slow splash screens or ads before the first useful action.
- **Example:** a language-learning app lets someone complete a one-minute lesson before creating an account, then offers to save their progress.

### Satisficing (p. 14)

People do not study the screen; they scan and click the first thing that looks good enough. This is rational: parsing a complex interface is work.

- **Signals:** almost always, especially first use and busy screens.
- **Moves:** explicit calls to action ("Paste a link here"); short, plain labels written so the first guess is right; layout and color that communicate meaning without reading; easy ways back from a hasty choice; less visual complexity.
- **Mistake:** clever or branded labels that users must decode.
- **Side effect:** users keep the first path they learned even when a better one exists. Do not expect them to discover improvements on their own.
- **Example:** a file-sharing page shows one large "Upload files" button and a drop zone; advanced options sit behind a small "More options" link.

### Changes in Midstream (p. 15)

Goals change during a task, by distraction or on purpose.

- **Signals:** browsing plus buying, long forms, multi-step processes.
- **Moves:** connect related content and actions instead of trapping people; support re-entrance: keep entered data, allow leaving and coming back, allow several work items open at once.
- **Mistake:** a flow that loses everything when the user steps out. Use locked-in flows (wizards, modal dialogs) only when there is a real reason.
- **Example:** a job application saves each section automatically; the candidate can go read the company page and return to the same step.

### Deferred Choices (p. 16)

Task-focused users want to skip questions that are not essential now, or that they cannot answer yet.

- **Signals:** registration, project setup, profile creation, checkout.
- **Moves:** ask only what is needed now; mark required versus optional clearly and keep required to a minimum; show the short list, tuck away the long list; use good defaults (remember that users still have to check them); make deferred settings easy to find later and say so; let people experience the product before asking them to register, and offer account creation at the end of a purchase.
- **Mistake:** a 12-field sign-up before the user can do the one thing they came for.
- **Example:** creating a new podcast episode needs only a title; artwork, tags and publishing schedule can be filled in afterwards.

### Incremental Construction (p. 17)

Creating is iterative: small pieces, step back, adjust, sometimes restart, rarely in order.

- **Signals:** editors, builders, configurators, code or design tools.
- **Moves:** cheap small edits, quick save, always show the whole result while working, near-instant feedback after a change. Good support enables *flow*, a state of deep absorption.
- **Mistake:** a slow preview or build step that breaks concentration every time.
- **Example:** a website builder updates the live preview as each block is edited instead of after a "Publish preview" step.

### Habituation (p. 18)

Frequent actions become reflexes. That makes experts fast, and it also sets traps.

- **Signals:** daily-use tools, gestures, keyboard shortcuts, confirmation dialogs.
- **Moves:** keep gestures and shortcuts consistent with the platform and within the product; never make the same gesture do something else in a special mode; prefer undo over confirmation dialogs, because a dialog that appears for every routine action gets dismissed by reflex exactly when it matters.
- **Mistake:** a swipe that archives on one screen and deletes on another.
- **Example:** a task app uses the same swipe direction for "complete" on every list and offers undo instead of asking "Are you sure?".

### Microbreaks (p. 19)

People fill a few spare minutes (waiting in line, between tasks) with something quick, mostly on mobile.

- **Signals:** feeds, news, messaging, casual games, reading, email triage.
- **Moves:** open fast; keep users signed in; show the freshest useful content on the first screen; restore exactly where they left off; for inbox-like content, make triage quick (enough information per item to decide, one-tap flag, delete, short reply). Load readable content first.
- **Mistake:** a login and a spinner every time the app opens.
- **Example:** a news app opens on the latest headlines from cache while new ones load, and the half-read article remembers its scroll position.

### Spatial Memory (p. 20)

People remember *where* something is more than what it is called.

- **Signals:** toolbars, menus, desktops, dashboards, repeated navigation.
- **Moves:** keep controls, menu items and navigation in the same place and order on every screen; adding things into empty space is safe, moving existing things is risky; let users arrange their own space and do not rearrange it for them; put items you want noticed at the start or end of a list, not the middle.
- **Mistake:** "smart" menus that reorder items by usage.
- **Example:** an admin console keeps the same left navigation order on every page and lets users pin favorite reports to a fixed area.

### Prospective Memory (p. 21)

People leave things in place to remind themselves to act later: an open tab, a flagged email, a note in a document.

- **Signals:** productivity, email, documents, task tracking, shopping.
- **Moves:** keep half-finished work; offer recent items, saved-for-later and bookmark-like lists; let people annotate and flag freely; consider gathering reminders from several sources in one place. Do not auto-close, auto-archive, auto-sort or "clean up" things users left on purpose.
- **Mistake:** a system that closes idle drafts or empties the cart without asking.
- **Example:** a shopping app keeps items in the cart across devices and shows "You left 2 items" on the home screen.

### Streamlined Repetition (p. 23)

When the same operation repeats, every saved click multiplies.

- **Signals:** data entry, bulk edits, moderation, media processing, admin work.
- **Moves:** one action per repetition, or one action for all (apply to all, batch selection, find and replace), recordable sequences or templates, copy and paste, shortcuts. Watch users work to spot repetition they no longer notice.
- **Mistake:** forcing the same five-step dialog for each of 50 items.
- **Example:** an expense tool lets users select ten receipts and assign the same project and category in one step.

### Keyboard Only (p. 24)

Some people cannot use a pointer, some use assistive technology that drives the keyboard interface, and some simply work faster without leaving the keys.

- **Signals:** data-entry tools, forms, accessibility requirements (always), power users.
- **Moves:** every function reachable from the keyboard; standard shortcuts for common commands; logical tab order; arrow-key selection in lists; a default action on Enter; in high-volume entry, move focus forward automatically.
- **Mistake:** actions available only on hover or drag.
- **Example:** an invoice form moves through fields with Tab, adds a line item with Enter on the last field, and saves with the platform's save shortcut.

### Social Media, Social Proof, and Collaboration (p. 25)

People are influenced by what peers do and recommend, and they value belonging and recognition.

- **Signals:** commerce, content, communities, team tools.
- **Moves:** reviews and ratings (rate the reviews too), showing activity by people the user knows, making any object shareable and commentable, collaboration features (threads, shared review, status tracking, live and asynchronous communication), community as part of help.
- **Mistake:** social features bolted on where nobody wants them, or fake popularity signals.
- **Example:** a recipe app shows "12 people you follow cooked this" and lets cooks attach photos and tips to each step.

## Choosing patterns for a brief

Pick the patterns that change the design, not every one that technically applies. Useful defaults:

| Product type | Usually central |
|---|---|
| First-use or onboarding flow | Instant Gratification, Deferred Choices, Satisficing, Safe Exploration |
| Checkout or transaction | Deferred Choices, Changes in Midstream, Satisficing, Social Proof |
| Editor or builder | Incremental Construction, Safe Exploration, Habituation, Spatial Memory |
| Daily professional tool | Habituation, Spatial Memory, Streamlined Repetition, Keyboard Only |
| Mobile feed or quick-check app | Microbreaks, Instant Gratification, Prospective Memory |
| Team or community product | Social Proof and Collaboration, Prospective Memory, Changes in Midstream |
