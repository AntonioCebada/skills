# Skills

This repository centralizes reusable opencode skills. Right now it contains a single skill, but the structure is meant to scale as more skills are added over time.

Language: [Español](./README.es.md)

## Current skills

| Skill              | Purpose                                                                                |
| ------------------ | -------------------------------------------------------------------------------------- |
| `design-md-author` | Analyze a project's visual identity and author or update a spec-compliant `DESIGN.md`. |

## Repository layout

```text
.
├── design-md-author/
│   ├── SKILL.md
│   ├── assets/
│   └── references/
├── docs/
└── README.md
```

## About the current skill

`design-md-author` is the first skill in this repository and it is the reason the repo exists today.

It helps turn a project's visual identity into a structured `DESIGN.md` by:

- extracting the brand voice, palette, typography, layout rhythm, and component language
- separating normative tokens from explanatory prose
- keeping the output aligned with the official `design.md` spec and local example patterns
- preserving uncertainty instead of inventing missing design facts

Its supporting files live inside the skill folder so the whole workflow stays self-contained:

- `design-md-author/SKILL.md` — the runtime instructions
- `design-md-author/references/` — distilled authoring notes and patterns
- `design-md-author/assets/` — templates and reusable starting points

## Notes

- Example materials used by a skill should live inside that skill's folder.
- This repo is for skill definitions and supporting references, not for application code.
