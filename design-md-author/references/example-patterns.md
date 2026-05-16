# Local example patterns for DESIGN.md

This file keeps the skill self-contained. It distills the local example `DESIGN.md` files stored under `design-md-author/examples/**` into reusable authoring patterns.

## Shared structural pattern

All three examples follow the same high-level approach:

1. Rich YAML frontmatter with:
   - `version`
   - `name`
   - `description`
   - `colors`
   - `typography`
   - `rounded`
   - `spacing`
   - `components`
2. Markdown body that explains the design system in prose.
3. Tokens first, rationale second.
4. Heavy reuse of token references inside `components`.

## Claude example pattern

Use this pattern when the identity is warm, editorial, humanist, and contrast-rich.

- Cream canvas + coral primary CTA.
- Serif display typography paired with a humanist sans body.
- Rounded but restrained surfaces.
- Component catalog is broad and product-marketing oriented: hero bands, mockup cards, pricing tiers, nav, cookie cards, inputs, tabs.

Authoring takeaway:
- When the brand voice comes strongly from type pairing and tone, make `Overview` and `Typography` unusually strong.
- Encode dark and light surfaces explicitly when the product switches surface families.

## NVIDIA example pattern

Use this pattern when the system is rigid, engineering-led, high-contrast, and rule-bound.

- Black/white dual-surface model.
- One aggressive accent color drives CTA and active states.
- Angular shapes with minimal radii.
- Dense technical/editorial grids with strict spacing.

Authoring takeaway:
- When a design language is defined more by constraints than decoration, say that directly in `Overview`, `Layout`, and `Shapes`.
- Keep tokens sparse and forceful rather than ornamental.

## xAI example pattern

Use this pattern when the system is minimal, dark, sparse, and relies on a small vocabulary repeated everywhere.

- Near-black full-canvas background.
- White pill-outline interaction model.
- Display sans + mono caption contrast.
- Accent palette exists but is intentionally rare.

Authoring takeaway:
- If the brand uses very few primitives, do not over-expand the token set.
- Document rarity and restraint, not just presence.
- Derived example components can be useful, but they must be labeled clearly if they are illustrative rather than directly observed.

## Reusable lessons

- Prefer semantic tokens over one-off literal names.
- Use `components` only for repeated or identity-defining patterns.
- When the UI has variants or states, model them as separate entries.
- Let prose explain usage, emphasis, and restraint.
- If evidence is incomplete, call out gaps rather than guessing.
