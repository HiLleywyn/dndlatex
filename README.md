# DnD Item Card LaTeX Template

A collection of LaTeX sources for printing item cards in the style of the fifth edition of "the world's greatest roleplaying game." The project packages card layouts, custom macros and example items so that you can quickly typeset professional looking handouts.

## Table of Contents
- [Features](#features)
- [Repository Layout](#repository-layout)
- [Requirements](#requirements)
- [Usage](#usage)
- [Creating New Cards](#creating-new-cards)
- [Known Issues](#known-issues)
- [License](#license)
- [Credits](#credits)

## Features
- Automatic pagination with mirrored backs for double‑sided printing.
- Item information lives in individual files for easy re‑use.
- Backgrounds and item art are fully customizable.
- Background images are clipped to each card and scale without stretching.
- Artwork panels use a dedicated `upperpart` box so backgrounds never bleed onto
  other cards.
- Long descriptions automatically shrink to fit the front side.
- Utility macros for item tags, flavor text, charges, spellcasting and more.

## Repository Layout
```
.
├── cards/                # Card definitions (one file per item)
├── img/                  # Background images
├── item_pics/            # Item art
├── dndItemCards.tex      # Main document to compile
├── itemCommands.tex      # Macros used in card files
├── tcolorboxSettings.tex # Layout configuration for cards
├── ExamplePage.png       # Example output
└── README.md             # Project documentation
```

## Requirements
This template requires a working LaTeX distribution such as TeX&nbsp;Live. `pdflatex` is recommended for compilation.

## Usage
1. Place item artwork in `item_pics/` and create a corresponding `.tex` file under `cards/`. Each card file defines commands such as `\cardtitle`, `\cardimage` and `\carddescfront`.
2. List the desired card file names in `\def\cardfiles{...}` within `dndItemCards.tex`.
3. Run `pdflatex dndItemCards.tex` to produce a PDF of the card sheet.

### Creating New Cards
Card files use the macros defined in `itemCommands.tex`. The most common commands are:
- `\ItemInfo{type}{rarity}{attune}{creature}[atk][def][school][dur][ac]` – item tags and property table in one command.
- `\FlavorText{flag}{text}` – italicised descriptive text.
- `\ChargeMechanics` and `\SpellCasting` – mechanics for charged and spell‑casting items.
- `\BonusText` and `\CurseText` – additional effects and curses.
- `\WeaponStatBlock{damage}{weight}{properties}` – table of weapon statistics.
- `\ArmorStatBlock{ac}{strength}{stealth}{weight}` – table of armor statistics.
- `\CreatureStats{ac}{hp}{speed}{str}{dex}{con}{int}{wis}{cha}{cr}` – simple creature or NPC stat block.
- `\CardPropertyBlock[atk][def][school][dur][ac]` – property table styled like `\WeaponStatBlock`; missing values display `N/A`.
- `\begin{upperpart} ... \end{upperpart}` – fixed-height box for artwork using
  `\cardbg` as its background.

See the existing files in the `cards/` directory for examples.

## Known Issues
Currently none.

## License
This project is released under the terms of the MIT License. See [LICENSE](LICENSE) for details.

## Credits
Based on work by DrailNecross and the [DnD 5e LaTeX Template](https://github.com/rpgtex/DND-5e-LaTeX-Template). Images are believed to be copyright free; please open an issue if you find otherwise.
