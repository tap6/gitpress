# gitpress

Open-source parts of [GitPress.net](https://gitpress.net): the theme spec,
builtin Astro themes, and the data-repository template.

The GitPress platform (login, WordPress-style admin, GitHub orchestration) is
closed source. This repo is what the platform and your own themes build on.

## Layout

| Directory | Contents |
| --- | --- |
| `spec/` | v1 spec: `gitpress.json` / `theme.json` JSON Schemas, frontmatter conventions, TS types |
| `themes/` | Builtin Astro themes: `classic`, `minimal`, `ink` |
| `templates/data-repo/` | Starting layout for a GitPress data repository |

## Compatibility

- All config files carry a `schemaVersion` / `specVersion`. New fields are
  always additive and optional; unknown fields must be ignored, not rejected.
- Sites pin a theme name + ref in `gitpress.json`; upgrading the platform
  never touches user repositories.
- Breaking changes only ship under a new major tag (this repo is tagged
  `v1`); `v1` stays backward compatible forever.

## Related

- [tap6/build-action](https://github.com/tap6/build-action) — the GitHub
  Action that builds a data repository with a theme from this repo and
  publishes the compiled site.
