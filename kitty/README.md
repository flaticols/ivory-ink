# Ivory Ink for Kitty

This folder contains Kitty ports of the Ivory Ink themes:

- `ivory-ink-light.conf` — high-contrast near-white light theme
- `ivory-ink-dark.conf` — high-contrast dark theme
- `light-theme.auto.conf` — Kitty auto light-mode file
- `dark-theme.auto.conf` — Kitty auto dark-mode file
- `no-preference-theme.auto.conf` — Kitty auto no-preference file, set to light mode

## Manual usage

Copy the theme files into your Kitty config directory:

```sh
cp ivory-ink-light.conf ivory-ink-dark.conf ~/.config/kitty/
```

Then include one theme from `~/.config/kitty/kitty.conf`:

```conf
include ivory-ink-dark.conf
```

or:

```conf
include ivory-ink-light.conf
```

Reload Kitty config with `ctrl+shift+f5`, or restart Kitty.

## Automatic light/dark mode switching

Kitty 0.38.0+ supports automatic theme switching based on the OS color scheme.

Copy all Kitty theme files from this folder directly into your Kitty config directory:

```sh
cp ivory-ink-light.conf \
   ivory-ink-dark.conf \
   light-theme.auto.conf \
   dark-theme.auto.conf \
   no-preference-theme.auto.conf \
   ~/.config/kitty/
```

Then restart Kitty.

Kitty will use:

- `dark-theme.auto.conf` when the OS is in dark mode
- `light-theme.auto.conf` when the OS is in light mode
- `no-preference-theme.auto.conf` when the OS reports no preference

Note: GNOME often reports `no-preference` unless “Dark style” is enabled, so `no-preference-theme.auto.conf` includes the light theme.

## Alternative: keep themes in a subfolder

If you prefer to keep the theme files in `~/.config/kitty/themes/ivory-ink/`, update the three `*.auto.conf` files to include relative paths, for example:

```conf
include themes/ivory-ink/ivory-ink-light.conf
```

and:

```conf
include themes/ivory-ink/ivory-ink-dark.conf
```
