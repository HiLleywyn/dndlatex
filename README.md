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
- Up to nine cards per sheet with mirrored backs for double‑sided printing.
- Item information lives in individual files for easy re‑use.
- Backgrounds and item art are fully customizable.
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
- `\ItemTags{type}{rarity}{attune}{creature}` – item tags and attunement requirements.
- `\FlavorText{flag}{text}` – italicized descriptive text.
- `\ChargeMechanics` and `\SpellCasting` – mechanics for charged and spell‑casting items.
- `\BonusText` and `\CurseText` – additional effects and curses.

See the existing files in the `cards/` directory for examples.

## Known Issues
- Currently limited to nine cards per sheet. Additional pages must be generated manually.
- Descriptions do not automatically overflow from the front to the back side.
- Slight spacing adjustments may be required when customising card sizes or graphics.
- Background images may appear stretched when non‑standard aspect ratios are used.

## License
This project is released under the terms of the MIT License. See [LICENSE](LICENSE) for details.

## Credits
Based on work by DrailNecross and the [DnD 5e LaTeX Template](https://github.com/rpgtex/DND-5e-LaTeX-Template). Images are believed to be copyright free; please open an issue if you find otherwise.
