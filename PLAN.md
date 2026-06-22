# IOS Extended Theme Localization and Rebrand Plan

## Summary
- Work only inside `Super26 Color (update 4.6)` and ignore `1.Super26 Pro`.
- Translate visible Vietnamese/Chinese UI text to precise English across theme metadata, lockscreen settings, AOD, clock, and runtime display strings.
- Rebrand public-facing metadata from `Super26 Color` / `DevInfinix` to `IOS Extended` / `DevInfinix`.
- Create public GitHub repo as `DevInfinix/IOS-Extended` with title `IOS Extended`.

## Key Changes
- Update `description.xml` title, author/designer fields, localized descriptions, Telegram, website, and GitHub links.
- Translate `lockscreen/advance/config.xml` visible `text`, `summary`, and safe `default` values while preserving existing XML shape, IDs, and duplicated/malformed attributes.
- Translate visible literal strings in `lockscreen/advance/manifest.xml`, `clock_2x4/manifest.xml`, `aod/content/manifest.xml`, and `miwallpaper/manifest.xml`.
- Leave internal resource paths and variable identifiers such as `DevInfinix_Ani`, `DevInfinix_effect`, `mSugerKey`, and image names unchanged unless every reference is updated and validation confirms no breakage.
- Disable the theme password gate only after mapping all `XIAOMITHEMEVIETNAMKEYPASS`, `mSugerKey`, and related key checks; do not touch Android system lock/unlock resources.
- Flag image assets that visibly contain old names, Vietnamese/Chinese text, or creator marks; do not edit images unless separately requested.

## GitHub and Docs
- Use `gh repo create DevInfinix/IOS-Extended --public` with description: `A Xiaomi theme with a modern iOS-inspired look for HyperOS devices.`
- Install/fix `git` first, because `gh` is authenticated but `git` is missing from PATH.
- Add `.gitignore`, `README.md`, and a custom restrictive license/no-redistribution notice.
- README will state the theme is an adapted and substantially modified project by DevInfinix, without misleading legal claims or hiding provenance.
- Use professional commits, for example:
  - `SETUP: Publish IOS Extended theme workspace`
  - `UPDATE: Refresh theme metadata and documentation`
  - `UPDATE: Translate lockscreen customization text`
  - `FIX: Remove theme password gate`
  - `UPDATE: Normalize runtime display strings`

## Validation
- Before editing: build a reference map for all old names, URLs, password keys, and non-English strings.
- After each edit batch: search for remaining `Super26`, `DevInfinix`, `DevInfinix`, `miuitheme`, old Telegram/Facebook links, and non-English visible strings.
- Validate XML files that are well-formed; for parser-sensitive one-line MAML files, preserve formatting and run targeted string/reference checks.
- Cross-check password removal by confirming no remaining active password prompt, key comparison, or unlock-gating expression.
- Report final risky leftovers, including unchanged internal asset paths and any image assets needing manual replacement.
