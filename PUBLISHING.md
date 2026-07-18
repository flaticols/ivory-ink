# Publishing Ivory Ink to Zed

Current extension metadata:

- Repo: `https://github.com/flaticols/ivory-ink`
- Extension ID: `ivory-ink-theme`
- Version: `0.2.0`

Zed currently publishes extensions through a PR to `zed-industries/extensions`.

## 1. Add the repo as a submodule

Use the extension ID as the submodule directory name, and use an HTTPS GitHub URL:

```bash
git submodule add https://github.com/flaticols/ivory-ink.git extensions/ivory-ink-theme
git add extensions/ivory-ink-theme
```

## 2. Add the registry entry

Add this to the top-level `extensions.toml` in `zed-industries/extensions`:

```toml
[ivory-ink-theme]
submodule = "extensions/ivory-ink-theme"
version = "0.2.0"
```

## 3. Sort registry files

From the `zed-industries/extensions` repo:

```bash
pnpm sort-extensions
```

## 4. PR checklist

- Keep the submodule URL as `https://github.com/flaticols/ivory-ink.git`
- Ensure `extension.toml` in this repo still has `id = "ivory-ink-theme"`
- Ensure the MIT `LICENSE` stays at the extension root
- If you change the theme before submission, bump `version` in `extension.toml` and use the same version in the registry entry
