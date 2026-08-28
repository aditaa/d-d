# Bellweather GM Assistant — SillyTavern Setup

This folder configures SillyTavern as a **behind-the-screen assistant for a human Game Master** running **The Lost Celebration of Bellweather**.

The human GM always controls the game. SillyTavern retrieves campaign details, prepares scenes, answers rules questions, tracks session state, suggests consequences, and writes short player-facing passages only when requested. It must not independently narrate, roll, resolve actions, portray NPCs, choose for the players, or advance the adventure.

> **GM-only material:** The character card, lorebook, and state files contain puzzle answers and campaign spoilers. Do not share this folder with players during the game.

## What to import

| File | Purpose | SillyTavern destination |
| --- | --- | --- |
| [Bellweather_GM_Assistant.json](characters/Bellweather_GM_Assistant.json) | Human-GM assistant Character Card V2. | **Characters → Import Character** |
| [The_Lost_Celebration_Lorebook.json](lorebooks/The_Lost_Celebration_Lorebook.json) | Campaign facts, scenes, clues, procedures, puzzle answers, stat blocks, rewards, and finale rules. | **World Info → Import** |
| [Human_GM_Authors_Note_Starting.txt](prompts/Human_GM_Authors_Note_Starting.txt) | Starting live-state record and assistant-only reminder. | Chat-specific **Author's Note** |
| [Human_GM_Session_State_Template.md](prompts/Human_GM_Session_State_Template.md) | Reusable state template for later scenes and sessions. | Copy the completed state into **Author's Note** |
| [Hero_Party_Reference.md](reference/Hero_Party_Reference.md) | Quick statistics and features for Bramble, Nyx, and Elio. | Human-GM reference; no import needed |

The [printable campaign README](../README.md), [complete adventure](../The_Lost_Celebration_Age_13_DnD_One_Shot.md), [maps](../maps/), and [PDF binder](../pdf/The_Lost_Celebration_Age_13_DnD_One_Shot.pdf) remain the authoritative game materials.

## Before you begin

This kit assumes SillyTavern is installed and connected to a text-generation model. If an ordinary imported character can reply, the connection is ready. This campaign requires no SillyTavern extensions, scripts, dice tools, or group chats.

For reliable campaign retrieval, use at least a 16,000-token context window; approximately 32,000 is preferable. Model settings vary, but a moderate temperature around 0.4–0.7 generally keeps factual assistant answers steadier. Start with a response limit around 800–1,500 tokens and ask for expanded preparation only when needed.

## Step 1 — Import the GM Assistant

1. Open SillyTavern.
2. Open the **Characters** panel.
3. Select **Import Character**.
4. Choose [characters/Bellweather_GM_Assistant.json](characters/Bellweather_GM_Assistant.json).
5. Open the imported **Bellweather GM Assistant** character.

If SillyTavern asks whether to import tags, either answer is safe. Tags only organize the character list.

## Step 2 — Import and link the lorebook

1. Open **World Info** using the globe icon.
2. Choose **Import**.
3. Select [lorebooks/The_Lost_Celebration_Lorebook.json](lorebooks/The_Lost_Celebration_Lorebook.json).
4. Return to the **Bellweather GM Assistant** character.
5. Click the character's globe button.
6. Choose **The_Lost_Celebration_Lorebook** as Character Lore and confirm.

The repository lorebook already contains a human-GM-assistant contract. **Do not disable or edit any lorebook entry after importing it.**

Importing the book is not enough by itself: it must be linked to the character so SillyTavern activates it whenever this assistant is open.

## Step 3 — Create the assistant chat

1. Start a new solo chat with **Bellweather GM Assistant**.
2. Open the options button beside the chat input.
3. Select **Author's Note**.
4. Copy the complete contents of [Human_GM_Authors_Note_Starting.txt](prompts/Human_GM_Authors_Note_Starting.txt) into the chat-specific Author's Note.
5. Set placement to **In-chat**, depth **1**, frequency **1**. If those controls are unavailable in your version, use **After Scenario**.
6. Send a GM request such as:

       Prep the opening commission. Do not start or narrate the scene.

The assistant should respond with information for you, not begin talking to the players.

## What the assistant should do

### Prepare a scene

Ask:

    Prep Briar Farm for me. Include the objective, visible details, challenge procedure, creature statistics, clues, consequences, reward, and next lead. Do not narrate the scene.

The answer should organize information for the human GM. You decide what to present and when.

### Retrieve an exact campaign fact

Ask:

    What does Captain Wick know about Lantern Gold?

    What is the exact Windmill answer and hint ladder?

    Give me Cindermaw's stat block and tactics.

GM-facing answers may include spoilers because the chat is behind the screen.

### Get player-facing text

Ask for it explicitly and state what the players currently know:

    Give me no more than 20 seconds of player-facing description for entering the Storehouse courtyard. The players know Wick suspects an impostor. Do not include hidden clues or mechanics.

The assistant should provide only the requested passage and stop. The human GM reads or adapts it at the table.

### Ask for a rule or ruling

Ask:

    Is Nyx eligible for Sneak Attack here? Separate the 2024 rule from your recommendation.

    How does Bramble's Protection reaction apply to this attack?

The assistant should label whether its answer is a **2024 rule**, a **campaign procedure**, or a **recommendation**.

### Ask for consequences or improvisation

Give the actual player action and roll:

    Nyx rolled 9 crossing the rafters. Give me two fail-forward consequences that preserve the Dawn Pearls. Label anything not printed in the adventure as suggested improvisation.

You remain responsible for choosing the result.

## During the game

SillyTavern is not the table and is not the GM. Continue running initiative, rolling dice, moving pieces, speaking as NPCs, and making final rulings yourself. Use the assistant when you need rapid retrieval or a second opinion.

A helpful rhythm is:

1. Run the scene at the table.
2. Ask the assistant a specific question only when needed.
3. Report important outcomes after the scene.
4. Ask it to produce an updated state block.
5. Check the block yourself before placing it in Author's Note.

Example state request:

    Update the human-GM session state. Dawn Pearls recovered; Silver Feather earned; Bramble 31 HP with one Second Wind remaining; Nyx and Elio are unhurt; Break 1 Short Rest is beginning. Do not add events I did not report.

## Saving and resuming state

The current Author's Note should contain what actually happened at your table. Chat history is useful context, but the state note wins if older messages conflict.

At a pause:

1. Open [Human_GM_Session_State_Template.md](prompts/Human_GM_Session_State_Template.md).
2. Ask the assistant to fill it from only the results you have reported.
3. Correct any HP, resources, clues, relationships, or decisions.
4. Replace the old chat-specific Author's Note with the corrected state.

When returning, ask:

    Using the current Author's Note, give me a GM-only status check and prep the next likely scene. Do not advance the game.

## Maps and print references

Keep the printable binder or relevant PDF open beside SillyTavern. Use the GM-keyed maps yourself and show only player-safe maps to players.

- [Briar Farm player map](../maps/Briar_Farm_Player_Map.png) and [GM keyed map](../maps/Briar_Farm_GM_Keyed_Map.png)
- [Lamplighter Storehouse player map](../maps/Lamplighter_Storehouse_Player_Map.png) and [GM keyed map](../maps/Lamplighter_Storehouse_GM_Keyed_Map.png)
- [Windmill puzzle map](../maps/Windmill_Chute_Puzzle_Map.png)
- [Honey Steps player map](../maps/Honey_Steps_Player_Map.png)
- [Founder's Hearth player map](../maps/Founders_Hearth_Player_Map.png) and [GM keyed map](../maps/Founders_Hearth_GM_Keyed_Map.png)
- [GM guide and stat blocks](../pdf/The_Lost_Celebration_GM_Guide_and_Stat_Blocks.pdf)

The three players continue using their printed character sheets. Do not create a SillyTavern Group Chat: Group Chats are for multiple AI characters, not three human players.

## Troubleshooting

### The assistant starts running the game

Confirm that the selected character is **Bellweather GM Assistant**, not an older autonomous Game Master card. Then replace the Author's Note with [Human_GM_Authors_Note_Starting.txt](prompts/Human_GM_Authors_Note_Starting.txt) or a current human-GM state block and send:

    Human GM mode is absolute. Stop narrating or advancing. Answer only my behind-the-screen questions unless I explicitly request player-facing text.

### The assistant cannot find campaign facts

Open the character panel, click the globe, and verify that **The_Lost_Celebration_Lorebook** is selected as Character Lore. The lorebook must be linked, not merely imported.

### The assistant invents details

Send:

    Separate printed campaign facts from suggested improvisation. If the campaign does not specify something, say so before offering options.

### The assistant gives player spoilers

State exactly what the players know and request player-facing text only. If needed, send:

    Player-facing text only. Remove puzzle answers, hidden motives, future events, DCs, and GM notes.

### The response is too long during play

Send:

    Answer first in no more than six bullets. I will ask if I need detail.

## Current SillyTavern references

- [Characters and importing](https://docs.sillytavern.app/usage/characters/)
- [World Info and Character Lore](https://docs.sillytavern.app/usage/core-concepts/worldinfo/)
- [Author's Note](https://docs.sillytavern.app/usage/core-concepts/authors-note/)
