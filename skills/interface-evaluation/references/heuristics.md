# The 10 usability heuristics

Reference for step 4 and step 6 of the workflow. These are broad principles for judging interfaces (Nielsen, Nielsen Norman Group). Explanations, questions and examples below are original. Each heuristic has: what it means, questions to ask while inspecting, typical failures, and the design patterns that usually fix them (pattern names from *Designing Interfaces*, 3rd ed., covered in the `interface-design` skill).

Contents:
- [1. Visibility of system status](#1-visibility-of-system-status)
- [2. Match between the system and the real world](#2-match-between-the-system-and-the-real-world)
- [3. User control and freedom](#3-user-control-and-freedom)
- [4. Consistency and standards](#4-consistency-and-standards)
- [5. Error prevention](#5-error-prevention)
- [6. Recognition rather than recall](#6-recognition-rather-than-recall)
- [7. Flexibility and efficiency of use](#7-flexibility-and-efficiency-of-use)
- [8. Aesthetic and minimalist design](#8-aesthetic-and-minimalist-design)
- [9. Help users recognize, diagnose and recover from errors](#9-help-users-recognize-diagnose-and-recover-from-errors)
- [10. Help and documentation](#10-help-and-documentation)
- [Quick triage: which heuristic?](#quick-triage-which-heuristic)
- [Heuristics and usability components](#heuristics-and-usability-components)

## 1. Visibility of system status

The system keeps people informed about what is happening, in reasonable time.

- **Ask:** After each action, can the user tell it registered? During waits, do they know something is happening and roughly how long? Can they tell where they are in a flow?
- **Typical failures:** a button that does nothing visible when tapped; a spinner with no end; an upload without progress; a multi-step form without step indicator; a state change (saved, sent) with no confirmation.
- **Fix direction:** immediate feedback on every action; progress indicators sized to the wait; clear "you are here" and "step 2 of 4"; confirmations that say what happened.
- **Patterns:** Visual Framework ("you are here" signposts), Instant Gratification, Incremental Construction (live preview), Microbreaks (fast load).

## 2. Match between the system and the real world

The interface speaks the users' language and follows real-world conventions: words, concepts and order that make sense to them, not to the system's internals.

- **Ask:** Would a first-time user understand every label without training? Do icons mean what people expect? Does the order of steps follow how people think about the task?
- **Typical failures:** technical jargon in messages ("null reference", "SKU"); internal department names as menu items; a trash icon that archives instead of deleting; dates and units in an unfamiliar format.
- **Fix direction:** research the audience's vocabulary and use it; use familiar metaphors only when they hold; order information the way users reason about it.
- **Patterns:** Satisficing (short, plain labels that guess right), Context research in "Designing for People".

## 3. User control and freedom

People make mistakes and change their mind; they need a clearly marked way out without a long process.

- **Ask:** Can every action be undone or cancelled? Is there a visible exit from every state (dialog, wizard, mode)? Does Back behave predictably? Can people leave a task and resume it?
- **Typical failures:** a flow without Cancel; destructive actions with no undo; a modal dialog with no close; a back button that restarts the form; auto-advancing carousels without pause.
- **Fix direction:** undo and redo; cancel and close in every modal state; keep entered data; confirm only the rare, truly irreversible actions, and prefer undo to "Are you sure?".
- **Patterns:** Safe Exploration, Changes in Midstream, Habituation (confirmation dialogs get clicked by reflex).

## 4. Consistency and standards

The same thing looks and behaves the same way everywhere (internal consistency), and the product follows platform and industry conventions (external consistency). People should not wonder whether different words or actions mean the same thing.

- **Ask:** Are labels, icons, colors and positions for the same function identical across screens? Does it follow platform norms (gestures, shortcuts, placement)? Do similar items look alike and different items look different?
- **Typical failures:** "OK" on one screen and "Accept" on another for the same action; a swipe that archives here and deletes there; the primary button on the left in one dialog and the right in another; custom controls that ignore platform behavior.
- **Fix direction:** define the rules once (design tokens, component library) and reuse; follow platform guidelines; reserve distinct styles for distinct meanings.
- **Patterns:** Visual Framework, Habituation, Spatial Memory, Similarity (Gestalt).

## 5. Error prevention

Better than a good error message is a design that stops the problem from happening, or catches it before it costs anything.

- **Ask:** Can the user easily trigger a harmful or irreversible action by mistake? Are impossible or invalid choices even offered? Are similar controls placed where they can be confused? Are defaults safe?
- **Typical failures:** Delete next to Save, same color and size; a free-text field where only a few values are valid; a date picker that allows a past date for a future booking; a form that discards data on a timeout.
- **Fix direction:** constraints (choose, don't type), sensible defaults, disabling unavailable actions with a reason, separating risky actions, and confirmation or undo for what remains. Check for slips (right goal, wrong action) and for mistakes (wrong goal or misunderstanding).
- **Patterns:** Responsive Enabling, Safe Exploration, Deferred Choices (good defaults), Spatial grouping by Proximity.

## 6. Recognition rather than recall

Minimize memory load: make elements, actions and options visible or easily retrievable, so people recognize instead of remembering.

- **Ask:** Does the user have to remember something from a previous screen? Are options visible when needed? Are instructions available where they apply? Are recent and frequent items offered?
- **Typical failures:** asking for a code shown two screens ago; icon-only navigation with no labels; hidden gestures with no hint; empty search with no recent searches or suggestions.
- **Fix direction:** show choices rather than ask for typing; label icons; keep context on screen (summary of the order while paying); offer history, suggestions and recently used.
- **Patterns:** Titled Sections and Visual Framework (visible structure), Spatial Memory, Prospective Memory (recents, saved-for-later).

## 7. Flexibility and efficiency of use

Shortcuts, hidden from novices, speed up expert use; the same interface serves both. Let people tailor frequent actions.

- **Ask:** Is there a faster path for frequent users (shortcuts, bulk actions, templates)? Does the simple path stay simple for beginners? Can frequent actions be personalized?
- **Typical failures:** forcing five screens for a task done fifty times a day; no keyboard access; no batch edit; no way to save repeated settings.
- **Fix direction:** shortcuts and accelerators, batch operations, saved views and templates, personalization, remembered preferences.
- **Patterns:** Streamlined Repetition, Keyboard Only, Movable Panels, Collapsible Panels.

## 8. Aesthetic and minimalist design

Screens should not contain information that is irrelevant or rarely needed. Every extra unit of information competes with the relevant ones and reduces their visibility. This is about focus, not about being austere.

- **Ask:** Is there one clear primary element? Does everything on the screen help the current task? Is the visual hierarchy readable at a glance?
- **Typical failures:** many banners and calls to action competing; walls of text; decoration that carries no meaning; low-contrast "subtle" text for essential information; five equally loud buttons.
- **Fix direction:** decide the primary element, demote or remove the rest; group and chunk; use progressive disclosure for the rare.
- **Patterns:** Center Stage, Titled Sections, Collapsible Panels, Accordion, visual hierarchy and Gestalt principles.

## 9. Help users recognize, diagnose and recover from errors

Error messages are written in plain language (no codes alone), say precisely what went wrong, and offer a constructive way forward.

- **Ask:** Is the error visible where it happened? Does the message say what is wrong and what to do? Is the user's input preserved? Is the tone neutral, never blaming?
- **Typical failures:** "Error 0x80070057"; "Invalid input" without saying which field or why; the form clears after an error; errors shown at the top far from the field; color alone marks the error.
- **Fix direction:** inline messages next to the field, in words the user would use; explain the cause and the fix ("Password needs at least 8 characters"); keep data; mark with text and icon, not only color.
- **Patterns:** Safe Exploration, Changes in Midstream (keep progress), Satisficing (clear labels), Proximity.

## 10. Help and documentation

It is best if the product needs no explanation, but when help is needed it should be easy to find, focused on the user's task, and short.

- **Ask:** Is help reachable from where the user is stuck? Is it searchable and task-based? Are first-use hints brief and dismissible?
- **Typical failures:** an 80-page PDF manual; help that opens on a generic home page; tooltips that repeat the label; onboarding that must be completed before use.
- **Fix direction:** contextual help, short task-oriented articles, search, examples; progressive onboarding; a way to reach a person when needed.
- **Patterns:** Instant Gratification (do not block first use with a tutorial), Social Proof and Collaboration (community support), help systems.

## Quick triage: which heuristic?

| What you observe | Start with |
|---|---|
| Nothing happens after a tap / user unsure if it worked | 1 |
| User does not understand a word, icon or order | 2 |
| User stuck, cannot go back or undo | 3 |
| Same thing looks or acts differently elsewhere | 4 |
| An easy mistake with costly results | 5 |
| User has to remember or search for options | 6 |
| Experts repeat many steps; no shortcuts | 7 |
| Screen is noisy; hard to see what matters | 8 |
| An error appears and the user cannot fix it | 9 |
| User needs to look up how to do something basic | 10 |

Notes on overlaps: unclear feedback after an error is 1 and 9; a destructive action with no undo is 3 and 5; a confusing label can be 2 (wrong language) or 4 (different from elsewhere). List all that apply, in one row.

## Heuristics and usability components

The five components of usability show *which kind of problem* a finding creates; use them to explain impact.

| Component | Question | Heuristics most related |
|---|---|---|
| Learnability | Can new users do basic tasks the first time? | 2, 6, 10, 1 |
| Efficiency | Once learned, how fast are tasks? | 7, 8, 4 |
| Memorability | Can returning users pick up where they left off? | 4, 6 |
| Errors | How many, how severe, how easy to recover? | 5, 9, 3 |
| Satisfaction | How pleasant is it to use? | 8, 1, 3 |

A sixth criterion, **utility** (does it do what the user needs?), sits beside these: a perfectly usable product that does the wrong thing still fails. Heuristic evaluation mostly finds usability problems, not missing features; mention utility gaps separately when you spot them.
