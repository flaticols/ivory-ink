# Ivory Ink for Zed

Ivory Ink is a Zed-native theme with paired light and dark variants:

- `Ivory Ink Light`
- `Ivory Ink Dark`

Its layered shell, editor, panel, and elevated surfaces evoke modern island-style IDE interfaces without copying another theme. A cool blue interaction color anchors focus and selection, while an original semantic palette separates keywords, functions, types, macros, strings, constants, and control flow.

The theme covers every property in Zed's current `v0.2.0` theme schema. It also includes:

- 13 distinct `accents` used by Git graph lanes, colorized brackets, and indent-aware guides
- complete built-in Tree-sitter capture coverage
- semantic-token styles such as `namespace.crateRoot`, `operator.controlFlow`, `function.special`, `type.builtin`, `type.interface`, and `type.parameter`
- coordinated diagnostics, collaboration colors, scrollbars, editor states, and ANSI terminal colors

## Semantic tokens

Zed currently disables semantic tokens by default. Set `"semantic_tokens": "combined"` globally or per language to apply semantic-token rules while retaining Tree-sitter highlighting as the base.

## Install as a dev extension

1. Open Zed.
2. Run `zed: install dev extension`.
3. Select this directory.
4. Open `theme selector: toggle` and choose `Ivory Ink Light` or `Ivory Ink Dark`.

## Files

- `extension.toml`: Zed extension manifest
- `themes/ivory-ink.json`: theme family containing both variants
