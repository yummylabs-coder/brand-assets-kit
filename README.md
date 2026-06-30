# Brand assets kit for Claude Code

Make Claude Code use **your real brand assets** in prototypes, instead of falling back to generic emojis and stock icons. Drop one folder into your project and Claude knows your logo, icons, and mascot, and when to reach for each one.

No code required to set it up.

## See it first

Open **`asset-preview.html`** in your browser. It shows every asset in the kit with a note on when each one is used. This is the fastest way to understand what you're getting, no terminal, no setup.

> Download or clone the repo, then double-click `asset-preview.html`. (You can also enable GitHub Pages on this repo to get a shareable live link to the preview.)

## What's inside

```
brand-assets/                  the folder you copy into your project
├── SKILL.md                   the brief Claude reads
├── assets/                    your real files live here
│   ├── logos/                 4 logo variants
│   ├── icons/                 10 interface icons
│   ├── mascots/               1 mascot, 4 poses
│   ├── patterns/              2 background patterns
│   └── illustrations/         4 spot illustrations
└── references/
    └── asset-manifest.md      tells Claude when to use each one
```

It ships with 24 neutral starter assets so it works the moment you install it. You swap them for your own brand, one file at a time.

## Quick start

**1. Copy the `brand-assets` folder into your project**, inside a folder called `.claude/skills/`:

```
your-project/
└── .claude/
    └── skills/
        └── brand-assets/      <- paste it here
```

Commit it to git and your whole team gets the same assets, with no extra setup. For personal use across all your projects, put it in `~/.claude/skills/` instead.

**2. Try it.** Ask Claude something like *"build me a success screen for my app."* It will use the celebration mascot from the kit instead of a party emoji.

## Make it yours

**Swap in your files.** Open the `assets/` folders and replace the starter files with your own. Use SVG where you can, since it stays sharp and recolors itself. Keep the names simple and lowercase, like `check-circle.svg`. You can do this gradually, the kit keeps working the whole way.

**Update the manifest.** Open `references/asset-manifest.md`. It has a row for every file. As you swap each one, update its line to describe your asset and when to use it, for example *"celebrating mascot, use on success screens."* This is the step that makes the whole thing work. A file Claude does not understand the purpose of is a file Claude will not use.

**Reopen the preview** any time to see your current library at a glance.

## Make Claude reach for it reliably (optional)

A skill loads on its own when your request matches it, but the trigger is not guaranteed every time. To make it dependable, add one line to your project's `CLAUDE.md`:

> For any UI, prototype, or screen work, use the brand-assets skill and check its asset-manifest before placing any graphic.

`CLAUDE.md` is read at the start of every session, so this keeps the skill top of mind. It does not load the assets into context, so it costs almost nothing. The assets still load only when Claude actually needs them.

## How it works

This is a Claude [Agent Skill](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview). At startup Claude only reads the skill's short description. It opens the full `SKILL.md` and the asset manifest only when your request involves building UI, and it loads individual asset files only when it places them. So the kit can hold a large asset library without filling up Claude's context. That design is called progressive disclosure.

## Who it's for

Designers, freelancers shipping client work, and small startups that don't have a design system yet. Anyone who prototypes in Claude Code and wants it to look like their actual product.

## License

MIT. Free to use, modify, and share. Built by [Yummy Labs](https://yummy-labs.com).
