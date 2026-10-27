# ux-compass

Agent skills that guide UI/UX design decisions. Load them into Claude Code or any agent that reads `SKILL.md` files, and the agent will design starting from the people who use the interface. Every layout choice comes with the user need and the principle behind it.

## Skills

| Skill | What it does | Status |
|---|---|---|
| [`interface-design`](skills/interface-design/SKILL.md) | Turns a brief into a user frame, the behavioral patterns that matter, a screen layout (hierarchy, grouping, flow, layout patterns) and a rationale table | Available |
| [`interface-evaluation`](skills/interface-evaluation/SKILL.md) | Reviews an existing interface with Nielsen's 10 heuristics, rates each problem's severity, and maps every fix back to a design pattern | Available |

## Install

With the [skills CLI](https://github.com/vercel-labs/skills):

```bash
npx skills add AndSanG/ux-compass
```

Or manually: copy `skills/interface-design/` into `~/.claude/skills/` (all projects) or `<project>/.claude/skills/` (one project). Other agents can read `skills/interface-design/SKILL.md` directly and follow its links to the reference files.

## What it looks like

Example prompts:

- "Design the home screen of an app that helps older adults book medical appointments."
- "Lay out an admin dashboard for a small store owner."
- "Where should the filters go on this product list, and should they be in an accordion?"
- "Here is my Figma frame description. Is the hierarchy right?"
- "Review these screenshots for usability problems and tell me what to fix first."

For a full request, the agent answers with:

1. **User frame**: audience, real goal, skill and motivation, context, with assumptions labeled.
2. **Patterns in play**: for example Instant Gratification or Deferred Choices, and the design move each implies.
3. **Layout**: primary, secondary and tertiary elements, page-level and chunking patterns, narrow-screen behavior.
4. **Rationale table**: decision, user need, principle, alternative rejected.
5. **Open questions** to test with real users.

Use them as a loop: design with `interface-design`, review with `interface-evaluation`, send the fixes back to the design patterns.

## Structure

```
skills/interface-design/
  SKILL.md                                workflow, quick pattern map, checklist
  references/designing-for-people.md      context, goals, research, 13 behavioral patterns
  references/screen-layout.md             hierarchy, grid, Gestalt, flow, regions, 8 layout patterns
  references/design-rationale-template.md template and a worked example
skills/interface-evaluation/
  SKILL.md                                method choice, workflow, report format, checklist
  references/heuristics.md                10 heuristics with questions, failures and fixes mapped to patterns
  references/severity-and-reporting.md   0-4 scale, finding format, worked example, user-test handoff
```

## Attribution

Heuristics and severity ratings follow J. Nielsen and R. Molich and the Nielsen Norman Group (nngroup.com), summarized in original words. Design patterns draw on concepts from J. Tidwell, C. Brewer and A. Valencia, *Designing Interfaces: Patterns for Effective Interaction Design*, 3rd ed. (O'Reilly, 2020), chapters 1 and 4. Pattern names are the authors'; the explanations, tables and examples here are original. This project is not affiliated with or endorsed by the authors or the publisher. Read the book for the full treatment.

## License

[CC BY 4.0](LICENSE). The license covers the text of this repository only.
