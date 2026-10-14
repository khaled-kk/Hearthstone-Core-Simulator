# Hearthstone Core Simulator

A two-player, hot-seat Hearthstone-style card game written in Java, with the game engine and card model separated from a Java Swing GUI.

## What it does

- Five playable heroes, each with a class-specific deck, legendary minion, and hero power:
  - **Hunter** (Rexxar) – Kill Command, Multi-Shot, King Krush
  - **Mage** (Jaina Proudmoore) – Polymorph, Flamestrike, Pyroblast, Kalycgos
  - **Paladin** (Uther Lightbringer) – Seal of Champions, Level Up!, Tirion Fordring
  - **Priest** (Anduin Wrynn) – Divine Spirit, Holy Nova, Shadow Word: Death, Prophet Velen
  - **Warlock** (Gul'dan) – Curse of Weakness, Siphon Soul, Twisting Nether, Wilfred Fizzlebang
- Decks are filled with neutral minions loaded from `neutral_minions.csv` (name, mana cost, rarity, attack, health, taunt, divine shield, charge).
- Turn logic in `engine.Game`: random first player, mana crystals that grow each turn (capped at 10), card draw, a 10-card hand limit, hero power once per turn, 30 HP heroes.
- Rule validation through the `ActionValidator` interface, with custom exceptions for invalid moves (not your turn, not enough mana, full hand/field, taunt bypass, invalid target, minion can't attack yet, hero power already used).
- Spells are modelled with interfaces by targeting type: `AOESpell`, `FieldSpell`, `HeroTargetSpell`, `MinionTargetSpell`, `LeechingSpell`.
- Listener interfaces (`GameListener`, `HeroListener`, `MinionListener`) connect the model to the engine and the GUI (e.g. minion death, hero death, game over).
- Swing GUI (`view.game`): hero selection with player names, buttons to play a minion, cast a spell, attack, use the hero power and end the turn; a pop-up announces the winner.

## Tech stack

- Java (Eclipse project, JavaSE-1.8)
- Java Swing / AWT for the GUI
- JUnit 4 for the tests in `src/tests`

## Repository contents

```
src/
  engine/       Game, ActionValidator, GameListener
  exceptions/   HearthstoneException and its subclasses
  model/
    cards/      Card, Rarity, minions/ (Minion, Icehowl), spells/ (Spell + individual spells and spell interfaces)
    heroes/     Hero (abstract), Hunter, Mage, Paladin, Priest, Warlock
  tests/        M1/M2 public and private JUnit test suites
  view/         game.java – Swing GUI and entry point (main method)
images/         Hero portraits, deck/card art and board backgrounds used by the GUI
neutral_minions.csv   Neutral minion data loaded into every deck
instructions.txt      How to play using the GUI
.classpath, .project, .settings/   Eclipse project files
```

## How to run

1. Import the folder into Eclipse as an existing project (**File > Import > Existing Projects into Workspace**).
2. Run `src/view/game.java` (class `view.game`) as a Java Application.

The working directory must be the project root, because `neutral_minions.csv` and the `images/` files are loaded by relative path.

From the command line (from the project root):

```bash
javac -d bin $(find src -name "*.java" -not -path "src/tests/*")
java -cp bin view.game
```

See `instructions.txt` for how to play.

---
*Developed by Khaled Walid*
