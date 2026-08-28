# The Lost Celebration — SillyTavern Setup

This folder turns **The Lost Celebration of Bellweather** into a SillyTavern campaign. It is written for someone who already has SillyTavern running but has never added a campaign before.

The recommended setup is one solo chat with **Bellweather Game Master**. You control Bramble, Nyx, and Elio as a party; the AI runs the world, NPCs, puzzles, and enemies. No SillyTavern extensions or scripts are required.

> **Spoiler warning:** The lorebook and Game Master card contain the adventure's solution, encounter answers, and finale. Players should not open those files.

## Files in this folder

| File | What it is | Where it goes |
| --- | --- | --- |
| [Bellweather_Game_Master.json](characters/Bellweather_Game_Master.json) | Importable Character Card V2 for the AI Game Master. | SillyTavern **Characters → Import Character**. |
| [The_Lost_Celebration_Lorebook.json](lorebooks/The_Lost_Celebration_Lorebook.json) | Importable World Info/lorebook containing scenes, clues, rules, statistics, and secrets. | SillyTavern **World Info → Import**. |
| [Authors_Note_Starting.txt](prompts/Authors_Note_Starting.txt) | Initial campaign-state reminder for the AI. | The new chat's **Author's Note** field. |
| [Session_State_Template.md](prompts/Session_State_Template.md) | Blank state record for saving, resuming, or correcting the AI's tracking. | Keep beside the chat; copy its state block into Author's Note when needed. |
| [Hero_Party_Reference.md](reference/Hero_Party_Reference.md) | Plain-text statistics and key actions for all three heroes. | Player reference; it does not need to be imported. |

The existing [campaign README](../README.md), [complete adventure](../The_Lost_Celebration_Age_13_DnD_One_Shot.md), [maps](../maps/), and [printable PDFs](../pdf/) remain the authoritative offline edition.

## Before importing the campaign

SillyTavern must be connected to a text-generation model before a character can answer. This campaign does not require a particular provider or model. If ordinary SillyTavern characters can reply, you are ready.

For best results, use a model with at least a 16,000-token context window. A larger context helps it remember combat and puzzle state, but the supplied Author's Note is still the authoritative current state.

## Step 1 — Import the Game Master

1. Open SillyTavern.
2. Open the **Characters** panel.
3. Select **Import Character**.
4. Choose [characters/Bellweather_Game_Master.json](characters/Bellweather_Game_Master.json).
5. Select the imported **Bellweather Game Master** character.

If SillyTavern asks whether to import the card's tags, either answer is safe. Tags only help organize the character list.

## Step 2 — Import and link the lorebook

1. Open **World Info** using the globe icon.
2. Choose **Import** and select [lorebooks/The_Lost_Celebration_Lorebook.json](lorebooks/The_Lost_Celebration_Lorebook.json).
3. Return to **Bellweather Game Master** in the Character Management panel.
4. Click the character's globe button and choose **The Lost Celebration of Bellweather** as its Character Lore.
5. Confirm the selection.

Linking the book to the character is important. Merely importing it does not guarantee that it will be active in this chat. SillyTavern's current documentation describes Character Lore as the character globe button and allows one primary World Info book to be linked there.

## Step 3 — Start the chat and add campaign state

1. Start a **new solo chat** with Bellweather Game Master.
2. Open the options button beside the message box and select **Author's Note**.
3. Copy all of [prompts/Authors_Note_Starting.txt](prompts/Authors_Note_Starting.txt) into the chat-specific Author's Note.
4. Set placement to **In-chat**, depth to **1**, and frequency to **1**. If your version only offers a placement choice, use **After Scenario**.
5. Reply to the Game Master's greeting with:

       Party mode. I will roll physical dice. Begin the adventure.

That is the complete required setup.

## Choose how to play

The opening message asks for two choices.

### Recommended: Party mode

You make decisions for all three heroes. Write one combined turn or list each hero's action separately. The AI never chooses an action for your heroes.

Example:

    Bramble blocks the barn door, Nyx climbs toward the rafters, and Elio tries the farmer's calming whistle.

### Optional: Single-hero mode

Choose Bramble, Nyx, or Elio. You control that hero while the AI Game Master runs the other two as helpful companions. The companions should support your choices rather than solve puzzles before you.

Example:

    Single-hero mode as Nyx. I will roll physical dice. Begin.

### Three human players at one screen

Use **Party mode** and give Bramble, Nyx, and Elio to different people. One person types each player's declared action and the resulting dice totals into the shared chat. Do **not** create a SillyTavern Group Chat for this setup: in SillyTavern, a Group Chat means several AI character cards, not several human logins.

Example:

    Bramble rolled 16 Athletics and braces the gate. Nyx rolled 18 Stealth and heads for the rafters. Elio scatters feed and rolled 12 Animal Handling.

### Dice choices

- **Physical dice:** the Game Master tells you what to roll, the modifier, and the DC when it is known. You reply with the die result or total.
- **Chat dice:** type a SillyTavern dice macro such as `{{roll::1d20+7}}`, then tell the Game Master the result. The macro is built into current SillyTavern releases.
- **Narrated dice:** tell the Game Master to roll for everyone. This is easiest, but an AI's narrated rolls should be treated as storytelling rather than independently verifiable randomness unless a dice extension or tool is active.

Do not install the optional D&D Dice extension just for this campaign unless you already want it; physical dice and the built-in roll macro are sufficient.

## How to write actions

State the hero, goal, and method. The Game Master will decide whether the idea works automatically or needs a check.

    Nyx checks the gold flask for the wooden-spoon seal without touching the blue fire.

    Bramble guards the Pearl Rune and uses Protection if a sootling attacks Elio.

    Elio offers Cindermaw a place as Bellweather's new hearth-keeper.

When a roll is requested, answer plainly:

    Nyx rolled 14 + 7 Stealth = 21.

During combat, include movement, action, Bonus Action, and intended Reaction only when relevant. The AI should announce initiative, current HP, conditions, and the next creature to act.

## Maps and character sheets

SillyTavern is handling narration and campaign memory, not acting as a battle-map application. Open the supplied files beside the chat:

- [Briar Farm player map](../maps/Briar_Farm_Player_Map.png)
- [Lamplighter Storehouse player map](../maps/Lamplighter_Storehouse_Player_Map.png)
- [Windmill puzzle map](../maps/Windmill_Chute_Puzzle_Map.png)
- [Honey Steps player map](../maps/Honey_Steps_Player_Map.png)
- [Founder's Hearth player map](../maps/Founders_Hearth_Player_Map.png)
- [Bramble character sheet](../pdf/Bramble_Stoneheart_Official_2024_Character_Sheet.pdf)
- [Nyx character sheet](../pdf/Nyx_Underbough_Official_2024_Character_Sheet.pdf)
- [Elio character sheet](../pdf/Elio_Starstring_Official_2024_Character_Sheet.pdf)

Only use the player maps while playing. The files whose names contain **GM_Keyed** reveal secrets and starting positions.

## Pausing and resuming

At the end of a scene, send:

    Pause the adventure. Give me a compact campaign-state block using the supplied template, without revealing future secrets.

Copy the returned state into the top section of [prompts/Session_State_Template.md](prompts/Session_State_Template.md), correct any mistakes, and replace the text in the chat's Author's Note. The chat history remains saved by SillyTavern, but this short state block prevents old details from displacing current HP, resources, and quest progress.

When returning, send:

    Resume from the current Author's Note. Recap only what the heroes know, then continue at the next decision.

## Correcting the AI without restarting

If the Game Master forgets a rule or advances too early, state the correction directly:

    Correction: Lantern Gold has been recovered, but Sunmeal has not. Update state and continue at the Windmill.

    Correction: Bramble has 21 of 37 HP and one Second Wind use left.

    Do not reveal the lost creation yet. Continue using only the component names.

You can also edit the most recent AI message or swipe to generate a replacement. Campaign state in Author's Note should win over conflicting older chat text.

## Troubleshooting this campaign

### The AI reveals the mystery too early

Confirm that the lorebook is linked, then add this line to Author's Note:

    Keep the finished creation secret until the Founder's Hearth dome opens; NPCs cannot confirm guesses.

### The AI chooses actions for the party

Send:

    Party mode: stop before every player decision and never choose Bramble's, Nyx's, or Elio's actions.

### The AI forgets hit points or quest items

Replace Author's Note with a corrected copy of the state template. Do not rely on old chat messages to override it.

### The lorebook seems inactive

Open Bellweather Game Master's Character Management panel, click the globe, and verify that **The Lost Celebration of Bellweather** is selected. The book should be linked as Character Lore, not merely present in the World Info list.

### The model writes too much

Send:

    Use one short scene description, necessary NPC dialogue, and one clear question. Stop before resolving any player choice.

## Optional human-table use

A human GM can use the same character as a quiet rules and scene assistant. Begin with:

    Assistant mode. I am the human GM. Do not narrate or advance the story unless asked. Answer only my campaign questions and provide spoiler-safe text when I request it.

For an in-person birthday game, the printable binder remains easier to run than typing every table action into SillyTavern.

## Current SillyTavern references

- [Characters and character importing](https://docs.sillytavern.app/usage/characters/)
- [World Info and linking Character Lore](https://docs.sillytavern.app/usage/core-concepts/worldinfo/)
- [Author's Note](https://docs.sillytavern.app/usage/core-concepts/authors-note/)
- [Macros, including dice rolls](https://docs.sillytavern.app/usage/core-concepts/macros/)
