# 🎲 Roll for Regret
### A Random D&D Character Generator by The Kobold Guild

*Because not every adventurer needs a tragic backstory. Sometimes, they're just called Dave.*

**Roll for Regret** is a free, browser-based random character generator designed for Dungeons & Dragons 5th Edition, primarily using the 2024 rules.

Whether you're a Dungeon Master in desperate need of an NPC, a player looking for inspiration, or someone who wants to discover what happens when the dice make all the decisions, this generator has you covered.

Create everything from heroic dragonborn paladins to suspiciously underdressed dwarves named Bark Wobblebottom.

## 🐉 Features

The generator randomly creates characters using a mixture of traditional D&D options and decidedly less traditional personality traits.

**Character details**
- First and last names, including mundane, elven, dwarven, draconic and ridiculous options.
- Species and background.
- Class and its corresponding subclass.
- Favourite weapon and armour.
- Personality traits.
- Height and body shape.
- Gender and sexuality.
- Omegaverse designation.

**Ability scores**

All six D&D ability scores are generated using **3d6**: Strength, Dexterity, Constitution, Intelligence, Wisdom and Charisma.

Each score totals three six-sided dice, giving a possible result between **3 and 18**. Only the final number is displayed, without modifiers or individual dice results.

**Optional 18+ rolls**

An optional adult section includes additional character anatomy rolls:
- Schlong Size: 1–13 inches.
- Breast Cup Size: EU letter categories from AA to N.

These fields are hidden by default and are independent of the character's gender.

## 🎮 How to Use the Generator

### Rolling a character

1. Open `index.html` in a browser, or visit the hosted website.
2. A random character is generated automatically.
3. Click **🎲 Roll Everything** to generate a new character.
4. Use **↻** beside any field to reroll that result individually.
5. Click **🔓** to lock a result you want to keep. A locked result shows **🔒** and stays unchanged when rerolling.

For example, if you've rolled a character named Doris Dragonscale and want to keep that magnificent name, lock the first and last name fields before rolling everything else.

### Choosing your own results

Dropdowns allow you to select a result instead of rolling, including names, classes, subclasses and other listed options.

Classes and subclasses are linked. Selecting a class automatically assigns a subclass belonging to it. **If a subclass is locked, unlock it before changing the class** to avoid incompatible combinations.

### Saving your character

- **Copy Character:** Copies the results as plain text, ready for notes, Discord or a character sheet.
- **Save JSON:** Downloads the results as a `.json` data file.
- **Print:** Opens the browser's print dialogue, where you can print or save as PDF.

The optional 18+ fields appear in copied or exported results only when their toggle is enabled.

JSON files are data exports, not saved character slots. The current version does not include a JSON import function.

## 💻 How the Code Works

Roll for Regret is built with **plain HTML, CSS and JavaScript**. No frameworks, external libraries, accounts or databases are needed. Everything is included in one file, `index.html`.

1. **HTML** defines the page structure, controls and character generator container.
2. **CSS** inside the `<style>` element controls the colours, typography, buttons and responsive layout.
3. **JavaScript** inside the `<script>` element defines the editable random tables, dice settings, character data and rolling functions.

The JavaScript arrays are visually grouped into numbered, commented sections. Edit these tables to customise the roller without changing its engine.

## ✏️ Editing the Random Tables

Open `index.html` with a plain-text editor such as Visual Studio Code, then search for these comments inside the `<script>` section:

- `SECTION 1: FIRST NAMES`
- `SECTION 2: SURNAMES`
- `SECTION 3: CLASS / SUBCLASS PAIRS`
- `SECTION 4: OTHER ROLL TABLES`
- `SECTION 5: DICE SETTINGS`
- `SECTION 6: OMEGAVERSE WEIGHTS`

Below the tables is the **GENERATOR ENGINE**, which ordinarily does not need editing.

### Adding names

Names are grouped by theme in `FIRST_NAMES` and `LAST_NAMES`, for example:

```javascript
"Ridiculous": [
  "Bang",
  "Bark",
  "Twork",
  "Bonk",
  "Clunk"
]
```

To add names, insert extra quoted entries separated by commas:

```javascript
"Ridiculous": [
  "Bang",
  "Bark",
  "Twork",
  "Bonk",
  "Clunk",
  "Boop",
  "Spud"
]
```

The generator combines the themed groups into one pool. Each individual name has an equal chance of being chosen, regardless of category.

### Editing classes and subclasses

Every class has its own subclass list in `SUBCLASSES`:

```javascript
"Druid": [
  "Circle of the Land",
  "Circle of the Moon",
  "Circle of the Sea",
  "Circle of the Stars"
]
```

Add homebrew subclasses by adding entries to the relevant list, such as `"Circle of the Mushroom"`. To add a class, give it a new key and subclass array within `SUBCLASSES`. The generator uses the keys as the class choices.

**Rules covered:** The 12 classes and 48 subclasses from the 2024 *Player's Handbook*, plus the updated Artificer and its five subclasses from *Eberron: Forge of the Artificer*.

### Editing other character traits

Additional lists are stored in the `CHOICES` object: species, weapons, armour, personality traits, body shapes, gender, sexuality, backgrounds and EU cup sizes.

For example:

```javascript
"Armour": [
  "Leather",
  "Chain mail",
  "Plate",
  "None at all",
  "Chainmail bikini"
]
```

Add new entries using the same format. Keep quotation marks and commas in the correct places.

### Changing dice settings

The `DICE_SETTINGS` object controls numerical rolls:

```javascript
const DICE_SETTINGS = {
  abilityDice: 3,
  abilitySides: 6,
  minHeightFeet: 2,
  maxHeightFeet: 8,
  inchesPerFoot: 12,
  adultMinInches: 1,
  adultMaxInches: 13
};
```

Changing `abilityDice` to `4` rolls four dice and totals all four. It **does not** automatically discard the lowest die.

### Editing Omegaverse probabilities

Omegaverse designations use weighted random results:

```javascript
const OMEGAVERSE = [
  { name: "Dominant Omega", weight: 5 },
  { name: "Recessive Omega", weight: 5 },
  { name: "Beta", weight: 60 },
  { name: "Dominant Alpha", weight: 15 },
  { name: "Recessive Alpha", weight: 15 }
];
```

The default is 10% Omega, 60% Beta and 30% Alpha. To use percentages, keep all weights adding up to 100. The generator uses relative weights, so other positive totals are also technically supported.

## 🎨 Changing the Appearance

The CSS uses colour variables at the top of `<style>`:

```css
:root {
  --ink: #073f37;
  --green: #005244;
  --mint: #41bea6;
  --cream: #efefdc;
  --magenta: #aa1b87;
  --paper: #fffdf4;
}
```

Change these values to customise your colours without rewriting all the CSS. The default design uses The Kobold Guild's green, mint, cream and magenta palette, with a mobile-friendly layout.

## 🌐 Running and Hosting

### Running locally

Open `index.html` in Chrome, Firefox, Edge or another modern browser. No installation or internet connection is required.

### Publishing with GitHub Pages

1. Create a GitHub repository.
2. Extract the ZIP file, then upload **`index.html`, `README.md` and `.nojekyll`** into the repository's **root** (not inside a nested folder).
3. In the repository, open **Settings → Pages**.
4. Select **Deploy from a branch**, then **main** and **/ (root)**, and save.
5. Visit your published GitHub Pages URL once deployment finishes.

The empty `.nojekyll` file instructs GitHub Pages to skip Jekyll processing. **Keep its leading dot**; it must be named `.nojekyll`, not `no.jekyll`.

### Updating the generator

1. Edit `index.html` in Visual Studio Code or directly on GitHub.
2. Find the relevant labelled array.
3. Save the file and open it in your browser to test the rolling buttons.
4. Commit the replacement `index.html` to GitHub.

A missing comma, quotation mark or bracket can stop JavaScript running, so check formatting if the roller stops generating results.

## ⚖️ Disclaimer

Roll for Regret is an unofficial fan-made utility inspired by Dungeons & Dragons. Dungeons & Dragons and associated game terminology belong to Wizards of the Coast. This project is not affiliated with or endorsed by Wizards of the Coast.

The generator is for entertainment, inspiration and tabletop roleplaying. Randomly generated combinations may not be mechanically legal or appropriate for every game.

Some results are deliberately silly, inappropriate or impractical. That's rather the point.

## 💚 About The Kobold Guild

**The Kobold Guild** creates human-made artwork, maps, adventures and resources for imaginary worlds.

Made for Dungeon Masters, players and anyone who enjoys giving an otherwise respectable fantasy character a name like Bonk Smith.

*Human-Made Art for Imaginary Worlds.*

**Created by The Kobold Guild**  
Website: https://thekoboldguild.com

---

**Happy rolling, and may your next adventurer be thoroughly regrettable.** 🎲
