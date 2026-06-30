# Asset Manifest

This is the source of truth for what assets exist and when to use each one. Read it before placing any graphic in a prototype.

The rows below describe the starter assets included in this kit. They work out of the box, so the manifest is accurate the moment you install it. As you swap each placeholder file for your own, update its row to match. The "use when" column is the important part: it is what tells Claude to reach for your celebration mascot instead of a party emoji.

## Logos

| File | Variant | Use when |
|---|---|---|
| `logos/logo-full.svg` | Full lockup (mark + wordmark) | Marketing pages, footers, email headers, anywhere with room |
| `logos/logo-mark.svg` | Icon mark only | App headers, favicons, tight spaces, avatars |
| `logos/logo-wordmark.svg` | Wordmark only | When the mark is already shown elsewhere on the screen |
| `logos/logo-mono-white.svg` | Single color, white | On photos, color blocks, and dark backgrounds |

Rules: never recolor the logo outside these variants. Never place the full lockup smaller than its minimum size (set your own, for example 120px wide).

## Icons

List your most-used icons so Claude knows they exist. Icons use `currentColor` and inherit the theme.

| File | Meaning | Use when |
|---|---|---|
| `icons/search.svg` | Search | Search inputs, find actions |
| `icons/settings.svg` | Settings | Settings entry points, filters, config |
| `icons/check-circle.svg` | Success / done | Confirmations, completed items, valid fields |
| `icons/alert-triangle.svg` | Warning | Caution messages, risky actions |
| `icons/x-circle.svg` | Error / remove | Failed states, dismiss, delete |
| `icons/arrow-left.svg` | Back | Back navigation, previous step |
| `icons/plus.svg` | Add | Create new, add item |
| `icons/menu.svg` | Menu | Navigation menus, more options |
| `icons/user.svg` | User | Profile, account, avatar fallback |
| `icons/calendar.svg` | Calendar | Dates, scheduling, date pickers |

Naming rule: name icons for what they mean, in kebab-case, so a missing one can be guessed (`arrow-left.svg`, `calendar.svg`, `user.svg`).

## Mascots

Map each pose or expression to a moment in the product. This is where Claude is most likely to fall back to an emoji, so be specific.

| File | Pose / expression | Use when |
|---|---|---|
| `mascots/mascot-celebrate.svg` | Celebrating | Success screens, completed onboarding, milestones reached |
| `mascots/mascot-thinking.svg` | Thinking | Loading states, processing, "we are working on it" |
| `mascots/mascot-shrug.svg` | Shrugging | Empty states, no results, page not found |
| `mascots/mascot-wave.svg` | Waving | Welcome screens, first run, sign-up |

Rule: if a moment calls for personality and no mascot pose fits, use a neutral placeholder and note the gap. Do not substitute an emoji.

## Patterns

Patterns need placement rules more than names.

| File | What it is | Use when | Rules |
|---|---|---|---|
| `patterns/dots-grid.svg` | Dotted grid | Section backgrounds, hero panels | Tileable. Max 8% opacity. Never behind body text |
| `patterns/wave-band.svg` | Wave divider | Between sections | Full width only. Use brand color |

## Illustrations

Map each spot illustration to the exact scenario it belongs to.

| File | Scenario | Use when |
|---|---|---|
| `illustrations/empty-inbox.svg` | Empty inbox | No messages, no notifications, cleared lists |
| `illustrations/no-results.svg` | No search results | Search returns nothing |
| `illustrations/error-500.svg` | Something broke | Error pages, failed loads |
| `illustrations/welcome.svg` | Welcome | Onboarding, first-time setup |

---

How to extend this manifest: when you add a file to `assets/`, add a row here in the same turn. An asset with no manifest row is invisible to Claude. The manifest, not the folder, is what makes the library usable.
