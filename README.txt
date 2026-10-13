# Roll for Regret
### A Random D&D Character Generator by The Kobold Guild

**Roll for Regret** is a free, browser-based random character generator designed for Dungeons & Dragons 5th Edition, primarily using the 2024 rules.
Whether you're a Dungeon Master in desperate need of an NPC, a player looking for inspiration, or someone who wants to discover what happens when the dice make all the decisions, this generator has you covered.
Create everything from heroic dragonborn paladins to suspiciously underdressed dwarves named Bark Wobblebottom.

## 🐉 Features

The generator randomly creates characters using a mixture of traditional D&D options and decidedly less traditional personality traits.

**Character Details**
- First and last names, including mundane, elven, dwarven, draconic and ridiculous options.
- Species and background.
- Class and its corresponding subclass.
- Favourite weapon and armour.
- Personality traits.
- Height and body shape.
- Gender and sexuality.
- Optional Omegaverse designation.

**Ability Scores**

All six D&D ability scores are generated using 3d6:

- Strength
- Dexterity
- Constitution
- Intelligence
- Wisdom
- Charisma

Each score is the total of three six-sided dice, giving a possible result between **3 and 18**. Only the final number is displayed, without modifiers or individual dice results.

**Optional 18+ Rolls**
An optional adult section includes additional character anatomy rolls:
- Schlong Size: 1–13 inches.
- Breast Cup Size: EU letter categories from AA to N. 
These fields are hidden by default and are independent of the character's gender.

## 🎮 How to Use the Generator

### Rolling a Character
1. Open the generator in your web browser.
2. A random character will be generated automatically.
3. Click **🎲 Roll Everything** to generate an entirely new character.
4. Use the ↻ button beside any field to reroll that result individually.
5. Use the 🔓 button to lock a result you want to keep. A locked field displays 🔒 and will not be changed by rerolling.

For example, if you've rolled a character named Doris Dragonscale and want to keep that magnificent name, lock the first and last name fields before rolling everything else.

### Choosing Your Own Results
Fields containing dropdown menus allow you to select a particular result rather than relying on random chance.
You can choose your preferred class, subclass, name, armour or other listed options.
Classes and subclasses are linked. Selecting a class automatically assigns a subclass belonging to it.
**Important:** If the subclass is locked, the class cannot be changed until you unlock the subclass. This prevents invalid class and subclass combinations.

### Saving Your Character
The generator offers three ways to keep your character:
- **Copy Character:** Copies the character's details as plain text, ready to paste into notes, Discord or a character sheet.
- **Save JSON:** Downloads the character's data as a `.json` file.
- **Print:** Opens your browser's print function to print the character or save it as a PDF.

The optional 18+ fields are only included in copied or exported results when the adult section is enabled.
JSON files are data exports, not saved character slots. The current version does not include an import function.

## 💻 How the Code Works
Roll for Regret is intentionally built using **plain HTML, CSS and JavaScript**.
There are no external libraries, frameworks, accounts or databases required.
Everything is contained inside a single file named `index.html`.
The file is organised into three main areas:

**1. HTML: Page Structure**
Defines the headings, controls and character generator container.

**2. CSS: Appearance**
Controls the colours, typography, buttons, spacing and responsive layout.

**3. JavaScript: Rolling System**
Contains the editable random tables, dice settings, character data and functions that make the generator work.
The JavaScript has been divided into clearly labelled sections, making it easier to modify
