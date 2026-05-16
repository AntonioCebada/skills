# Skills

Este repositorio centraliza skills reutilizables de opencode. Hoy contiene una sola skill, pero la estructura está pensada para crecer con más skills en el futuro.

Idioma: [English](../README.md)

## Skills actuales

| Skill              | Propósito                                                                                                  |
| ------------------ | ---------------------------------------------------------------------------------------------------------- |
| `design-md-author` | Analizar la identidad visual de un proyecto y redactar o actualizar un `DESIGN.md` compatible con la spec. |

## Estructura del repositorio

```text
.
├── design-md-author/
│   ├── SKILL.md
│   ├── assets/
│   └── references/
├── docs/
└── README.md
```

## Sobre la skill actual

`design-md-author` es la primera skill de este repositorio y la razón principal de su existencia.

Ayuda a convertir la identidad visual de un proyecto en un `DESIGN.md` estructurado al:

- extraer la voz de marca, la paleta, la tipografía, el ritmo de layout y el lenguaje de componentes
- separar tokens normativos de la prosa explicativa
- mantener la salida alineada con la spec oficial de `design.md` y con los patrones de los ejemplos locales
- preservar la incertidumbre en vez de inventar datos visuales faltantes

Sus archivos de apoyo viven dentro de la carpeta de la skill para que el flujo sea autocontenido:

- `design-md-author/SKILL.md` — instrucciones de runtime
- `design-md-author/references/` — notas y patrones destilados
- `design-md-author/assets/` — plantillas y puntos de partida reutilizables

## Notas

- Los materiales de ejemplo usados por una skill deben vivir dentro de su propia carpeta.
- Este repositorio es para definiciones de skills y referencias de apoyo, no para código de aplicación.
