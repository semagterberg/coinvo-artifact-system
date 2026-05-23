# Coinvo Artifact System

A locked visual system for the Coinvo Operator Framework, Company Blueprint, and any brand document that needs embedded artifacts.

**This repo is the source of truth.** A bootstrap skill in claude.ai clones this repo on every artifact request, reads the spec, views the gallery, and builds new artifacts that match. To evolve the system, evolve this repo. The skill never needs touching again.

## Structure

| Path | Contents |
|---|---|
| `spec.md` | The full system spec: palette, type scale, components, patterns, creative method, workflow, anti-patterns. The binding text reference. |
| `principles.md` | Why decisions were made. Inheritance of judgment, not just rules. |
| `evolution.md` | Changelog of the system itself, so future sessions do not recreate past mistakes. |
| `gallery/` | PNG screenshots of approved artifacts. The binding visual reference. |
| `references/` | HTML source of approved artifacts. Code recipes. |
| `anti-examples/` | PNGs of rejected artifacts with a sidecar note explaining what went wrong. |
| `issues/` | Drop a rejected screenshot here with a one-line "why" filename, future sessions read this on session start. |

## How to add a new approved artifact

1. Screenshot it from your chat
2. Save with a descriptive name like `the-[topic].png`
3. Drag into `/gallery/` via GitHub's web UI
4. Commit

Done. Next session sees it.

If you also have the HTML source (the widget code I generated in chat), drop that into `/references/` with a matching filename like `[topic].html`. Strongly recommended because it gives future sessions the code recipe, not just the visual.

## How to flag something that went wrong

1. Screenshot the rejected artifact
2. Save with a descriptive filename like `terminal-style-too-dim.png` or `title-40px-out-of-proportion.png`
3. Drag into `/anti-examples/` (permanent "do not") or `/issues/` (one-off fix)
4. Optional: add a `.md` sidecar with a one-line explanation

## The 6 locked colors (quick reference)

Full spec in `spec.md`.

| Hex | Name | Semantic role |
|---|---|---|
| `#34D399` | Green | Active, amplify (Breaking News, REPLY, RETWEET, +AMPLIFY) |
| `#22D3EE` | Cyan | Lead, authority (Original Content, Credibility, foundation) |
| `#F5C518` | Yellow | Calibration, boost (Stealing Winners, VIDEO WATCH, +BOOST) |
| `#A855F7` | Purple | Compound, signal (Double Down, Signal Brand, replay loop) |
| `#F97316` | Orange | Stream, viral (Video Content, Viral Chaser, parallel system) |
| `#F04848` | Red | Penalty, death (BLOCK, dead account, -PENALTY) |

**Bucket-to-color is locked across the Operator Framework.** Do not reassign. Breaking is always green, Original is always cyan, Stealing is always yellow, Double Down is always purple, Video is always orange.

## How the bootstrap skill works

The claude.ai skill `coinvo-artifact-system` is a 30-line bootstrap that runs on every artifact request:

```bash
git clone --depth 1 https://github.com/semagterberg/coinvo-artifact-system.git /tmp/cas
```

Then reads `spec.md`, views relevant gallery PNGs, reads relevant reference HTMLs, and follows the workflow. The skill is the bootstrap, this repo is the system.

## Versioning the system

Every meaningful change to the spec, palette, or method gets an entry in `evolution.md` with date, what changed, and why. Future sessions read this so they inherit not just the current state but the reasoning behind it.

## License

Personal reference repo for Sem and Coinvo. No license attached. Public for read access only.
