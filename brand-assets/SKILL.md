---
name: brand-assets
description: "Use your real brand assets in prototypes instead of generic emojis, stock icons, or placeholder graphics. Load this whenever building, prototyping, or styling any UI, screen, component, landing page, empty state, success state, or error state. Triggers on: prototype, build a screen, mockup, landing page, empty state, loading state, success screen, error screen, add an icon, add a logo, add an illustration, hero section, onboarding. Also use any time a graphic, icon, logo, mascot, or pattern is about to be placed in an interface."
---

# Brand Assets

This skill gives Claude your real, on-brand assets so prototypes look like your product instead of a generic template. When Claude is about to drop in a graphic, it checks here first instead of reaching for an emoji or a stock icon.

This kit ships with a full set of starter assets that already work, so it is useful the moment you install it. Swap them for your own brand one file at a time, and update the manifest as you go. That is the whole setup.

Try it right away: ask Claude to build a success screen, an empty state, or a landing hero, and it will pull from `assets/` instead of reaching for emojis.

## Critical rule

Never use an emoji, a Unicode symbol, or a generic stock icon as a stand-in for a brand asset. If a screen needs an icon, a logo, a character, a pattern, or an illustration, use the matching file from `assets/`. If no asset fits the need, use a plain neutral placeholder and say so in one line, so the gap is visible and can be filled later. A visible gap is fixable. A wrong-but-plausible emoji ships to a client.

## How to use the assets

Every asset lives in `assets/` as an SVG where possible. Reference files by their path, for example `assets/icons/check-circle.svg`. For inline UI, import the SVG directly so it stays sharp and recolorable. Vectors inherit color through `currentColor`, so an icon can match the surrounding text or theme without editing the file.

Use raster files (PNG) only for assets that cannot be vectors, such as detailed mascot art or photographic textures.

## The manifest: which asset, when

The most important part of this skill is matching the right asset to the right moment. A folder of files is not enough on its own, because the file names alone do not say when each one is meant to be used. The manifest does.

The full intent-to-asset table lives in `references/asset-manifest.md`. Read it before placing any graphic. It maps a need ("a success state", "an empty inbox", "the app logo on a dark header") to the exact file to use.

Keep the manifest updated whenever assets are added or replaced. It is the single source of truth for what exists and what each asset is for.

## Brand basics

Fill these in once. Claude uses them so every prototype stays consistent.

- Brand name: [YOUR BRAND NAME]
- Primary color: [#HEX]
- Secondary / accent color: [#HEX]
- Background, light mode: [#HEX]
- Background, dark mode: [#HEX]
- Headline font: [FONT NAME]
- Body font: [FONT NAME]

## What goes in each folder

**logos/** Your logo in every variant you have: full lockup, icon mark only, wordmark, and a single-color version. The rule that matters most here is which variant goes where. Example: full lockup in the top-left of marketing pages, mark only in tight spaces like an app header or a favicon, single-color version on photo backgrounds.

**icons/** Interface icons, one SVG per icon, named for what they mean (`search.svg`, `settings.svg`, `check-circle.svg`). Keep the naming consistent so Claude can find an icon by guessing its name. Icons should use `currentColor` so they pick up the theme.

**mascots/** Your brand character, if you have one, in each pose or expression. This is the asset Claude is most likely to replace with an emoji, so the manifest entries matter most here. Map each pose to a moment: celebrating for success, thinking for loading, shrugging for empty or not-found.

**patterns/** Background textures, decorative shapes, repeating motifs. These need placement rules more than names: where they are allowed, whether they tile, and a maximum opacity so they never fight the content.

**illustrations/** Larger spot graphics for specific scenarios: empty states, onboarding screens, error pages, feature highlights. Map each one to the scenario it belongs to.

## Naming convention

Match your design tool. If the component in your design file is `icon/check-circle`, name the file `check-circle.svg`. Names are the link between your design source and your prototypes. Consistent names make the asset library predictable, which is what lets Claude reach for the right file without being told each time.

Use kebab-case: lowercase words joined by hyphens. No spaces, no capitals.

## Keeping a single source of truth (for teams)

Place this whole `brand-assets/` folder inside your project at `.claude/skills/brand-assets/` and commit it to git. Everyone on the team who pulls the repo gets the same assets and the same usage rules, with no extra setup. When the brand updates, update the files here, commit, and the whole team is in sync.

For personal use across all your own projects, place it at `~/.claude/skills/brand-assets/` instead.

## Make Claude reach for it reliably (optional)

A skill loads on its own when your request matches its description, but that trigger is not guaranteed every time. To make it dependable, add one line to your project's `CLAUDE.md`:

> For any UI, prototype, or screen work, use the brand-assets skill and check its asset-manifest before placing any graphic.

`CLAUDE.md` loads at the start of every session, so this short nudge keeps the skill top of mind. It does not copy the assets into context. The heavy content still lives in the skill and loads only when it is actually needed.

## Quick check before shipping a prototype

- Did every graphic come from `assets/`, not an emoji or stock icon?
- Did the logo variant match its placement (dark background, tight space, etc.)?
- Are any gaps called out in plain language so they can be filled?

---

Made by Yummy Labs. More tools for designers at yummy-labs.com
