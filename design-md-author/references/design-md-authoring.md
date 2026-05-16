# DESIGN.md authoring reference

This note is the local reference for the `design-md-author` skill. It summarizes the structure and authoring rules extracted from the official `google-labs-code/design.md` repository and should be treated as the source of truth inside this skills repo.

## What a DESIGN.md is

`DESIGN.md` is a plain-text, self-contained representation of a design system for both humans and coding agents.

It has two layers:

1. **YAML frontmatter** with machine-readable design tokens.
2. **Markdown body** with human-readable rationale, intent, and usage guidance.

Core rule:
- **Tokens are normative values.**
- **Prose explains why those values exist and how to apply them.**

## Canonical structure

### Frontmatter

Use YAML delimited by `---` fences.

Supported schema:

```yaml
version: alpha            # optional
name: <string>
description: <string>     # optional
colors:
  <token-name>: <Color>
typography:
  <token-name>: <Typography>
rounded:
  <scale-level>: <Dimension>
spacing:
  <scale-level>: <Dimension | number>
components:
  <component-name>:
    <property>: <literal | token reference>
```

### Body sections

Sections are optional, but included sections must appear in this order:

1. `Overview` or `Brand & Style`
2. `Colors`
3. `Typography`
4. `Layout` or `Layout & Spacing`
5. `Elevation & Depth` or `Elevation`
6. `Shapes`
7. `Components`
8. `Do's and Don'ts`

## Token authoring rules

### Colors
- Prefer semantic roles such as `primary`, `secondary`, `tertiary`, `neutral`, `surface`, `on-surface`.
- `primary` is strongly expected and avoids linter warnings.
- Use exact values when they can be observed from the source project.

### Typography
- Capture a real hierarchy, not every incidental text size.
- Each token may include `fontFamily`, `fontSize`, `fontWeight`, `lineHeight`, `letterSpacing`, plus optional `fontFeature` and `fontVariation`.

### Rounded and spacing
- Model the reusable scale, not one-off measurements unless they are central to the system.
- Use descriptive keys (`sm`, `md`, `xl`, `gutter`, `margin`, `container-padding`).

### Components
- Add only repeated or identity-defining components.
- Preferred properties: `backgroundColor`, `textColor`, `typography`, `rounded`, `padding`, `size`, `height`, `width`.
- Express states as separate entries, for example `button-primary`, `button-primary-hover`, `button-primary-active`.
- Prefer references such as `{colors.primary}` and `{typography.body-md}`.

## Prose authoring rules

### Brand & Style / Overview
- Describe personality, audience, emotional tone, and stylistic movement.
- This is the fallback guidance when exact tokens do not answer a design choice.

### Colors
- Explain role and usage of each palette family.
- Mention contrast, emphasis, and semantic intent.

### Typography
- Explain hierarchy, readability strategy, and special treatments.

### Layout
- Explain rhythm, grid logic, spacing philosophy, and container behavior.

### Elevation & Depth
- Explain how hierarchy is achieved: shadows, tonal layers, borders, blur, glow, or flatness.

### Shapes
- Explain corner philosophy, geometry, icon edge treatment, and tactile feel.

### Components
- Summarize behavior and styling guidance for the most important recurring components.

### Do's and Don'ts
- Add only when the project has clear guardrails or recurring mistakes worth encoding.

## Consumer and validation behavior

- Unknown section headings are tolerated and preserved.
- Unknown token names are acceptable if their values are valid.
- Unknown component properties may be tolerated with warnings.
- Duplicate section headings are errors.
- Out-of-order sections may lint as warnings.

## Practical extraction workflow

1. Identify visual evidence from UI, screenshots, code, or docs.
2. Infer the brand narrative from copy, palette, type, density, motion, and surface treatment.
3. Capture only stable design primitives first.
4. Add component tokens for repeated patterns.
5. Write prose that teaches an agent how to apply the system, not just what tokens exist.
6. If evidence is partial, be explicit about uncertainty instead of inventing values.

## Notes about real-world examples

The official examples are slightly more permissive than the strict written type descriptions. They sometimes use values like `rgba(...)`, `transparent`, or multi-value padding strings. Follow the observed project conventions when they are clearly present, but keep the document internally consistent and grounded in evidence.
