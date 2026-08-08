# Ivory Ink for Zed

Ivory Ink is a Zed-native theme with paired light and dark variants:

- `Ivory Ink Light`
- `Ivory Ink Dark`

Its layered shell, editor, panel, and elevated surfaces evoke modern island-style IDE interfaces without copying another theme. A cool blue interaction color anchors focus and selection, while an original semantic palette separates keywords, functions, types, macros, strings, constants, and control flow.

## Palette system

Both variants are generated from one OKLCH specification, so they are recognizably the same theme:

- **Nine role hues** — red, orange, amber, green, jade, cyan, azure, violet, magenta — at fixed hue angles. Every syntax role maps to the same hue in light and dark; only lightness and chroma change. Concrete types read amber; interfaces, type parameters, labels, and lifetimes read jade.
- **Equal perceptual lightness.** Code colors sit in a tight L\* band (light ~47–50, dark ~79), so no token shouts louder than its neighbours. Comments, doc comments, and inline predictions are deliberately held below that band while still clearing 4.5:1.
- **Warm ivory surfaces, blue-black ink.** Shell, panel, and editor share one warm neutral ramp; text carries a faint cool cast.
- **Contrast comes from lightness, not saturation.** Chroma is capped below the sRGB gamut edge, so the theme stays composed on wide-gamut Display P3 panels, where Zed's unmanaged Metal layer drives sRGB values straight into P3 primaries.

### Editor highlight ladder

Selection states step monotonically instead of blending together, and each is hue-coded so you can tell them apart at a glance:

| State | Hue | Contrast vs editor background |
| --- | --- | --- |
| Active line | neutral | 1.07× / 1.09× |
| Highlighted line | neutral | 1.20× / 1.23× |
| Symbol occurrence (read) | azure | 1.42× / 1.54× |
| Matching bracket | cyan | 1.55× / 1.75× |
| Symbol occurrence (write) | magenta | 1.68× / 1.96× |
| Selection | azure | 1.85× / 2.24× |
| Search match | amber | 1.98× / 2.38× |

Symbol highlights stay legible even when the caret is parked on the highlighted line, where the tint composites over the active-line background.

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
