# Notices and Attributions

This project bundles game data and icons derived from third-party sources.
The original source code of this project is MIT-licensed (see
[LICENSE](LICENSE)). The following third-party materials retain their own
licenses and require attribution.

---

## Game IP

**Monster Hunter Generations Ultimate** and all related characters, item
names, monster names, weapons, and other in-game assets are trademarks and
© Capcom Co., Ltd. This project is an **unofficial fan-made weapon-tree
viewer**. It is not affiliated with, endorsed by, or sponsored by Capcom.

---

## Game Data

### Weapon stats, names, and upgrade trees

Every weapon's stats, level names, rarity, and parent/upgrade linkage
bundled in this project (embedded at build time from
[mhgu-collection-tracker](https://github.com/ArmoredRaven17/mhgu-collection-tracker)'s
`docs/data/stats/`, `docs/data/materials/`, and `docs/data/catalog.js`) trace
back to two sources documented in that project's own NOTICE.md:

- **[Kiranico](https://mhgu.kiranico.com/)** — weapon names and stat tables.
  Kiranico does not publish a formal data license; this attribution is
  offered as courtesy acknowledgment of their fan-database work.
- **[JoeLago/MHGUDB-iOS](https://github.com/JoeLago/MHGUDB-iOS)** (MIT) and,
  upstream of that, **[gatheringhallstudios/MHGenDatabase](https://github.com/gatheringhallstudios/MHGenDatabase)**
  — crafting-material recipes and English item naming.

Only the factual stat and recipe data is re-emitted, in this project's own
compact schema, for the classes it currently embeds (Bow, Light/Heavy
Bowgun, and the nine Blademaster weapons). No source code or original
schema from those projects is redistributed.

### Weapon-branch mechanic

Branches that unlock mid-upgrade stay open past that level rather than
closing — a real game mechanic `mhgu.db` does not record (it stores only the
level a branch first appears). The later edges are derived in this
project's own code from that single data point; see the `BRANCH` /
`options()` logic in `docs/index.html`.

---

## Icons and Visual Assets

### Weapon rarity icons (all 14 classes × 11 rarities)

Sourced from mhgu-collection-tracker's `docs/assets/icons/`, which pulls
them from
[Category:MHGU Equipment Icons](https://monsterhunterwiki.org/wiki/Category:MHGU_Equipment_Icons)
on the independent **Monster Hunter Wiki** (monsterhunterwiki.org),
licensed **[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)**.
By the share-alike clause, this project's bundled copies remain under the
same licence.

### Coating icons (8 files) and shot/ammo colour sampling

The coating chip icons, and the reference colours used to derive the ammo
and shelling palettes, come from
[mhgu-editor](https://github.com/ArmoredRaven17/mhgu-editor)'s
`public/icons/colored/MH4G-Coating_Icon_*.png` and
`MH4G-Shot_Icon_*.png`. That project sources them from the **Monster
Hunter Fandom wiki** (monsterhunter.fandom.com), licensed
**[CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)**.

### Hunting Horn note icons (8 files)

Vector note glyphs from mhgu-editor's `public/icons/hh_notes/`. These
appear to be original artwork created for that project rather than
wiki-sourced; if that is mistaken, please open an issue.

### Theme-picker monster icons (27 files) and background textures

The 27 monster portrait icons, the MHFU-style background textures
(`rockyTextureDark2`, `banner-background`, `titlebar-background`), and the
titlebar/theme-modal layout are carried over from
[MHGU Quest Randomizer](https://github.com/ArmoredRaven17)'s `assets/`
folder (same author). That project does not currently document the
original provenance of these specific files; the monster icons' naming
convention matches the Fandom-sourced icons documented above, so the same
CC BY-SA 3.0 attribution is offered here as a best effort pending
confirmation. If you can source these more precisely, please open an issue.

### Font

The MHFU display font under `docs/index.html` (embedded, not a separate
file) is a fan-made recreation of the Monster Hunter interface typeface,
carried over from the MHGU Quest Randomizer project — see that project's
own notes for provenance.

### Sharpness colours

The sharpness-bar colours and band labels (Base/S+1/S+2) reuse
mhgu-collection-tracker's own `SHARP_COLORS` constant (`docs/app.js`) so a
weapon's sharpness reads identically in both apps.

---

## Colour system

### Theme engine

The titlebar, monster-swatch theme picker, and the accent-hue derivation
(one chosen colour, every surface's shade computed by role rather than by
scaling the accent's own lightness) are adapted from
[MHGU Quest Randomizer](https://github.com/ArmoredRaven17)'s `app.js` and
`styles.css` (same author). The lightness ranges were substantially
reworked for this project — see the `ROLE` table in `docs/index.html` — to
fix contrast and distinctness issues the original per-surface formula had
across this app's full colour range.

### Reload / Recoil / shot-pattern colouring

The rule that ranks an ordered stat (Reload, Recoil, Deviation) across
hue 0°→120° by position rather than by name, and the level-shaded shot
colours (Rapid/Pierce/Spread/Heavy, Gunlance shelling), are ported from
the **[MHFU Look Up](https://github.com/ArmoredRaven17)** app's
`WeaponViewModel.cs` (same author, C#/WinUI project) — see `ScaleBrush`,
`AmmoBrush`, and the charge-level brush logic in that file.

---

## Development — AI assistance

A large share of this project's source code was written with
**[Claude Code](https://claude.com/claude-code)** (Anthropic), directed and
reviewed by the author.

This is disclosed for transparency rather than to satisfy a licence term.
The project's code remains MIT-licensed (see [LICENSE](LICENSE)).

---

## Reporting Misattribution

If a person, project, or organization is misattributed or omitted from this
notice, please open an issue on the project repository and the file will be
updated.
