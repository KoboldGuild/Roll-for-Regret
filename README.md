# Roll for Regret — The Kobold Guild

A completely static, browser-based D&D character concept generator, ready to host using **GitHub Pages**. No backend, packages, API keys, Node.js installation or build process required.


## Character creator features

- 100 first names & 100 surnames
- Stats: individually rerollable 3d6 Strength, Dexterity, Constitution, Intelligence, Wisdom and Charisma
- species
- class and class-matched subclass
- background
- weapons
- armour
- personality
- motivation
- 2–8 ft height, with 0–11 additional inches
- body type
- gender & sexuality
- Additional tables for: Omegaverse roll (10% Omega, 60% Beta, 30% Alpha); and an optional 18+ anatomy roll. Includes editable fields, full reroll, clipboard copy, JSON download and printing.

## Classes & subclasses (2024 rules)

Every time you roll a class, the generator also rolls a subclass belonging to that class. You can independently reroll the subclass, or pick a different valid subclass from its dropdown. Selecting a different class immediately selects a new subclass. The printed view, clipboard export and JSON export all include it.

- **2024 Player's Handbook:** 12 core classes, 4 subclasses per class (48 total).
- **Eberron: Forge of the Artificer (2025):** updated Artificer with Alchemist, Armorer, Artillerist, Battle Smith and Cartographer (5 total).
- **53 subclasses altogether.** All subclasses in these 2024-compatible sources are available in the random tables. Subclasses are generally acquired at level 3; this concept generator does not model character levels or full subclass rules.

Official source references (names only, not reproduced game rules):
- https://www.dndbeyond.com/posts/1810-updates-in-the-players-handbook-2024
- https://www.dndbeyond.com/posts/2106-whats-new-with-the-artificer-in-eberron-forge-of

## Customise

- Edit name lists and random choices near the top of `js/script.js`. Class-specific options live in the `subclasses` object. Add a new class to `tables.className` and give it an entry in `subclasses` to expand the lists.
- Change the appearance in `css/style.css`.
- Edit page text and headings in `index.html`.

This generates *character concepts* and is not a complete rules-legal D&D 5e character builder. Some flavour options are intentionally silly. The mature-content control is off by default.
