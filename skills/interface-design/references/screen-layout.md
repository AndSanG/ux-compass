# Screen layout

Reference for step 3 of the workflow. Concepts from *Designing Interfaces* (3rd ed.), chapter 4; page numbers point to that edition. Explanations and examples are original.

Contents:
- [What a layout must communicate](#what-a-layout-must-communicate)
- [Visual hierarchy](#visual-hierarchy)
- [Grid and alignment](#grid-and-alignment)
- [Gestalt grouping](#gestalt-grouping)
- [Visual flow](#visual-flow)
- [Dynamic displays](#dynamic-displays)
- [UI regions](#ui-regions)
- [Page-level patterns](#page-level-patterns): Visual Framework, Center Stage, Grid of Equals
- [Chunking patterns](#chunking-patterns): Titled Sections, Module Tabs, Accordion, Collapsible Panels, Movable Panels
- [Chunking decision guide](#chunking-decision-guide)

## What a layout must communicate

A layout places content, controls, framing elements and decoration on the screen (p. 209). Whatever the screen size, a viewer should understand at a glance:

1. what matters most,
2. what belongs together,
3. what to do next.

A layout people call "clean" usually combines four things: a clear visual hierarchy, a deliberate visual flow, alignment to a grid, and Gestalt grouping.

## Visual hierarchy

The most important element stands out the most and the least important stands out the least; the structure of the information should be readable from the layout alone (pp. 209-210). Quick test: blur the screen or replace the content with gray boxes. If you can still tell what is primary, the hierarchy works.

Tools for signaling importance (pp. 211-215):

| Tool | How it signals | Practical rule |
|---|---|---|
| Size | Bigger reads as more important | Make heading levels clearly different; small text reads as fine print |
| Position | Top and top-left (in left-to-right cultures) get seen first | Put the primary element where the eye lands first; footer-like zones read as minor |
| Density | Spacing shows what is related and how calm the screen feels | Tight spacing inside a group, more space between groups; avoid uniform spacing everywhere |
| Background and contrast | A tinted block or strong contrast pulls the eye | Use it for one or two things; if everything is highlighted, nothing is |
| Rhythm | Repeated lists, grids and alternating heading and summary pairs draw the eye along | Use repetition for peer items so scanning becomes effortless |
| Emphasis on small items | Small elements stand out at the top, along the left, or in the top-right corner, with contrast and whitespace | Inputs (search, sign-in) and big buttons draw attention by meaning, even when small |

## Grid and alignment

Designing on a grid gives visual consistency and balance, lowers cognitive load, makes responsive behavior easier and lets several designers work on related screens coherently (pp. 216-217). A grid is defined by **margins** (space around the content) and **gutters** (space between columns or rows). Every element should snap to it; misalignments read as mistakes or as unintended relationships.

## Gestalt grouping

Four perception principles explain why some things look related (pp. 217-220):

| Principle | What people perceive | Use it to |
|---|---|---|
| Proximity | Things close together belong together; isolation means separate | Keep labels next to their fields and actions next to what they affect; separate unrelated groups with space |
| Similarity | Things alike in shape, size or color are related or of the same kind | Give peer items an identical treatment; mark one special item with a small difference (tinted background, a badge, breaking the alignment slightly) while keeping it consistent otherwise |
| Continuity | The eye follows lines and curves formed by aligned edges | Align items in a column or row to make them read as a sequence |
| Closure | The mind completes incomplete shapes, including shapes made of whitespace | Use whitespace and alignment to form groups without drawing boxes around everything |

They work best together: aligned edges create a line (continuity), and if the aligned items enclose a region, closure strengthens the group further.

## Visual flow

Visual flow is the path the eye takes across the screen; hierarchy creates the stops, flow connects them (pp. 220-223).

- Default reading order (top to bottom, left to right in Western scripts) applies on uniform pages; strong focal points override it.
- Keep **focal points few**: each extra one dilutes the others. Order them strongest to weakest along the path you want.
- Use implied lines (alignment, direction of shapes or of a person's gaze in a photo, arrows) to lead from one element to the next.
- If you want people to read a value proposition, place its parts along one continuous path and do not interrupt it with eye-catching extras.
- In forms and tool areas, do not scatter controls; place the main action right after the content the user reads before acting. If reading first does not matter, isolate the action with whitespace instead.
- Symptom of bad flow: many elements competing, and no clear answer to "where do I look first?".

## Dynamic displays

Screens are smaller than posters but can change over time and respond to the user (pp. 223-225):

- **Scrolling** gives a viewport onto large content. Avoid horizontal scrolling for text.
- **Chunking with interaction** (tabs, accordions, panels) lets the user choose what is shown; see the chunking patterns below.
- **Responsive enabling:** controls become available only once a prerequisite choice is made, guiding the process and preventing invalid states. Use it carefully where spatial memory matters: enabling in place is fine, moving controls around is not.
- **Progressive disclosure:** detail appears only after a related action (for example, formatting options appear once the user selects text). Keeps the first view simple without removing power.

## UI regions

Most screens draw on the same regions (pp. 225-226):

| Region | Typical content | Notes |
|---|---|---|
| Header or title bar | Identity, global navigation, sometimes toolbars | Persists across screens, so be selective; this space is expensive |
| Menu or navigation | Sections and destinations | Top or left side; can be a panel |
| Main content area | The information, form, task or canvas | Gets most of the space |
| Panels | Tools, properties, filters, details | Top, side or bottom; persistent or dismissible |
| Footer | Secondary or repeated navigation, contact, legal | Low priority by position |

## Page-level patterns

Decide these first, since they shape every screen (pp. 226-227). Choose by content and user goal: search results and catalogs suggest a Grid of Equals; tasks, creation and productivity suggest Center Stage. Both live inside a Visual Framework.

### Visual Framework (p. 228)

- **What:** all screens share the same skeleton and style: regions, margins, spacing, colors, type, writing style, and the place of signposts and navigation, while leaving room for varying content.
- **Use when:** there is more than one screen, which is almost always.
- **Why:** users stop re-learning the layout on every screen; constant elements fade into the background so the changing content stands out; a distinctive framework also carries the brand.
- **How:** define once and reuse: color roles, type scale (title, subtitle, body, callout, minor), voice and grammar rules; "you are here" signposts (titles, current-section indicator, breadcrumbs); navigation devices (global and utility navigation, back and exit, progress indicators); section styling; spacing and alignment rules; column and row structure. The home or main screen may differ but still shares these traits. Implement it in one place (design tokens, a stylesheet, a component library) so it can change without touching content.
- **Example:** a clinic portal where appointments, results and billing pages share the same header, left navigation, card style and button placement, so patients always find "Back" and the primary action in the same spot.

### Center Stage (p. 231)

- **What:** the main task or content takes the largest area; secondary tools and information take the narrower areas around it.
- **Use when:** the screen exists mainly to show one coherent thing or to perform one task: a document, a map, a table, a form, a canvas, a single article or video.
- **Why:** one clear anchor tells users immediately what the screen is for; they then interpret the surroundings in relation to it instead of scanning around in confusion.
- **How:** make the central area clearly dominant; as a rule of thumb, at least twice as wide as the side areas and twice as tall as the top and bottom ones, as first displayed. It should own most of the space above the fold, even on small screens. A strong headline at its top can anchor the eye. Exact position matters less than size; follow genre conventions for the margins (toolbars above editors, navigation on the left).
- **Example:** a route-planning screen where the map fills the screen and the trip details sit in a narrow side or bottom sheet.

### Grid of Equals (p. 235)

- **What:** many items of similar kind and importance in a grid, each built from the same template with similar visual weight, each linking to its detail.
- **Use when:** listing products, articles, courses, properties, videos, or other peers the user will compare and choose from.
- **Why:** equal space says equal importance; a shared template says "these are the same kind of thing", and once a user understands one card they understand all.
- **How:** design one card first (image? title? subtitle? price? summary?) and fit it into a compact shape; then decide columns per breakpoint and check narrow widths. Highlight a featured item or the hovered one with color or style, never by changing card size, position or structure.
- **Example:** a course catalog where every course card shows the same cover, title, duration and level in the same spots.

## Chunking patterns

Ways to split content that does not fit comfortably (pp. 227-228). All of them depend on getting the grouping right first: coherent chunks with short, memorable names.

### Titled Sections (p. 238)

- **What:** content divided into visually separated blocks, each with a strong title; everything stays visible.
- **Use when:** there is a lot of content, but users benefit from seeing it all and scanning it.
- **Why:** named chunks make the structure obvious and guide the eye down the page.
- **How:** titles that clearly differ from body text (weight, size, color, family or indentation); separate sections with whitespace or tinted backgrounds; boxes and lines only sparingly, since nested or crowded boxes become noise. If the page still overwhelms, move to tabs, accordion or collapsible panels.
- **Warning sign:** if a chunk is hard to name, or you need "Miscellaneous", the grouping is probably wrong.
- **Example:** an account settings page with sections "Profile", "Security", "Notifications" and "Payments".

### Module Tabs (p. 242)

- **What:** modules share one area and only one is visible at a time; tabs switch between them.
- **Use when:** users need only one module at a time; modules are of similar size; there are few of them (fewer than 10, ideally a handful); the set rarely changes.
- **Why:** declutters the screen while keeping alternatives discoverable.
- **How:** split by what users need side by side; a bad split forces constant tab switching to compare. Keep labels to one or two words. Make the selected tab unmistakable (connected to its panel; color alone is not enough, especially with two tabs). Tabs can sit on top, on the left or below. If they do not fit: shorten labels, scroll the tab row, or move them to a left column. Never stack tabs in two rows. In-page module tabs are different from navigation tabs that load other pages.
- **Example:** a product page with "Description", "Specifications" and "Reviews" tabs under the main product information.

### Accordion (p. 245)

- **What:** a vertical stack of titled modules, each opening and closing independently.
- **Use when:** users may want several modules open at once; modules vary in height but share width; the order of modules matters; they form a coherent set (a tool palette, a two-level menu, an FAQ).
- **Why:** declutters long, structured content and lets users shape their own workspace while keeping rarely used modules one click away.
- **How:** concise but descriptive titles; a clear expand affordance (chevron or triangle); allow several modules open at once (closing one automatically when another opens surprises users and blocks comparison); in apps or signed-in sites, remember which modules were open. Beware: with large or many open modules, the lower titles scroll out of view.
- **Example:** a help center where each question expands to its answer, so users scan all questions on one screen.

### Collapsible Panels (p. 249)

- **What:** secondary or optional modules in panels the user can open and close; closing returns the space to the main content.
- **Use when:** modules support, explain or modify the main content (often a Center Stage); they are optional, valued differently by different users or at different times; several may be open; and they are not closely related to each other.
- **Why:** simplifies the screen and gives priority to the main content: progressive disclosure at panel level.
- **How:** one click to toggle, labeled with the module's name (or "More") plus a chevron or similar icon; collapse fully when closed; animate opening and closing so users learn where the panel lives; if most users open a panel that is closed by default, make it open by default.
- **Example:** a document editor with a comments panel on the right that slides closed for distraction-free writing.

### Movable Panels (p. 252)

- **What:** modules in titled boxes the user can open, close, rearrange and sometimes remove or add.
- **Use when:** a desktop app or a signed-in site with a screen people use often or for long periods (dashboards, portals, canvas-plus-palette tools); many modules of very different size; interests vary a lot between users; module position matters to users more than to you.
- **Why:** people arrange their workspace to fit how they work and then rely on spatial memory to find things; personalization also raises engagement; new modules can be added over time.
- **How:** every module has a title bar with its name and a starting size, placed in a sensible default layout. Allow drag and drop and a one-click open/close. Decide between free placement and a grid of slots (slots keep things aligned and save fiddling; show drop targets while dragging). If modules can be removed, provide a browsable list to add them back.
- **Example:** an operations dashboard where each person keeps their own arrangement of charts, alerts and task lists.

## Chunking decision guide

Synthesis to choose quickly among the chunking patterns:

| Question | Titled Sections | Module Tabs | Accordion | Collapsible Panels | Movable Panels |
|---|---|---|---|---|---|
| Everything visible at once? | Yes | No, one module | Some, user decides | Main content always; extras on demand | User decides |
| Several modules open together? | n/a | No | Yes | Yes | Yes |
| Modules related to each other? | Yes, as one page | Yes, alternatives | Yes, one set | No, independent extras | Varies |
| Module sizes | Any | Similar | Similar width, any height | Any | Very different |
| Order or position matters? | Yes, designer decides | Fixed | Yes, linear | Fixed around main content | User decides |
| Typical place | Settings, long pages | Product details, preferences | FAQ, side menus, tool palettes | Editors, maps, comment side panels | Dashboards, creative tools |
| Main risk | Overwhelming length | Splitting what users must compare | Lower titles scrolling away | Hiding something most users need | Fiddly setup; needs a sign-in to persist |
