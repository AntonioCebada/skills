---
name: design-md-author
description: "Trigger: DESIGN.md, identidad visual, visual identity, design system, brand analysis. Analyze a project's visual identity and author or update a spec-compliant DESIGN.md."
license: Apache-2.0
metadata:
  author: AntonioCebada
  version: "1.0"
---

# design-md-author

## Activation Contract

Use this skill when the task is to inspect an existing product, site, UI, or brand and turn its visual identity into a `DESIGN.md` file. Use it for net-new files, gap-filling incomplete `DESIGN.md`, or normalizing ad-hoc style notes into the canonical format.

Do not use it for generic UX critique, logo redesign, or code-only theming changes without a `DESIGN.md` deliverable.

## Hard Rules

- Treat `references/design-md-authoring.md` as the local source of truth for structure and rules.
- Use `examples/**/DESIGN.md` as shape references, not as content to copy.
- Keep the file dual-layered: YAML frontmatter for normative tokens, Markdown body for rationale and usage guidance.
- Preserve observed facts. If something is inferred, mark it as inferred and choose conservative wording.
- Sections may be omitted only when evidence is missing, but any included sections must follow canonical order.
- Prefer token references like `{colors.primary}` over duplicated literals inside `components`.
- Never invent implementation details you cannot support from the analyzed project.

## Decision Gates

| Condition                                          | Action                                                                         |
| -------------------------------------------------- | ------------------------------------------------------------------------------ |
| Strong visual evidence from UI, styles, or docs    | Write concrete tokens and guidance                                             |
| Partial evidence only                              | Fill known sections, keep scope narrow, mark gaps explicitly                   |
| Existing `DESIGN.md` present                       | Update it in place, preserve valid sections and normalize order only when safe |
| Repeated components/states are visible             | Add `components` tokens and separate variant keys like `button-primary-hover`  |
| No trustworthy palette/type scale can be extracted | Stop short of fabrication and report what is missing                           |

## Execution Steps

1. Inspect the project artifacts that reveal identity: live pages, screenshots, design docs, CSS/Tailwind/theme files, component libraries, and brand copy.
2. Extract stable primitives first: brand personality, palette roles, typography hierarchy, spacing rhythm, corner radii, elevation model, and recurring components.
3. Write or update YAML frontmatter with `name`, then the smallest justified token set from `colors`, `typography`, `rounded`, `spacing`, and `components`.
4. Write the Markdown body in canonical order: `Overview` or `Brand & Style`, `Colors`, `Typography`, `Layout` or `Layout & Spacing`, `Elevation & Depth`, `Shapes`, `Components`, optional `Do's and Don'ts`.
5. In prose, explain intent and usage, not raw token dumps. In tokens, prefer exact values and reusable references.
6. Cross-check against `references/design-md-authoring.md` and compare shape/level of detail with `examples/**/DESIGN.md`.
7. If the repo has the official CLI available, recommend or run `npx @google/design.md lint DESIGN.md` to validate structure.

## Output Contract

Return:

- The created or updated `DESIGN.md` path.
- What evidence sources were used.
- Which sections/tokens are confirmed vs inferred.
- Any missing evidence that prevented fuller coverage.

## References

- `design-md-author/references/design-md-authoring.md`
- `design-md-author/references/example-patterns.md`
- `design-md-author/assets/DESIGN.template.md`
- `design-md-author/examples/claude-design/DESIGN.md`
- `design-md-author/examples/nvidia-design/DESIGN.md`
- `design-md-author/examples/xai-design/DESIGN.md`
