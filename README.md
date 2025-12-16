Janitor Script Builder (v0.2.7)

Launch the Live Tool: https://mellowflloww.github.io/JanitorAI-Script-Builder/

> Advanced scripting made easy. Fill out simple forms, generate complex JavaScript, and copy-paste directly into JanitorAI. No coding knowledge required.

> What is this?

JanitorAI allows bot creators to use "Advanced Scripts" (JavaScript) to modify character behavior, memory, and narration dynamically. However, writing JavaScript is hard.

Janitor Script Builder is a visual interface that writes the code for you. It runs entirely in your browser (Client-Side)—no data is ever sent to a server.

New in v0.2.7
 * Complete UI Overhaul: Now matches the native JanitorAI theme.
 * Script Tester: Test your scripts directly in the tool before adding them to your bot.
 * Trigger Analyzer: Automatically find conflicts between your keywords.

🛠 The Modules
You can use just one module, or combine them all into a single "Master Script."

1. 📖 Lorebook (Context Engine)
Goal: Efficiently manage world info without bloating the context.
 * How it works: Detects keywords in user messages and injects specific details into the scenario only when relevant.
 * Best for: RPG inventories, location descriptions, NPC appearances.

2. 🧠 Memory System
Goal: Fake "long-term memory" and user recognition.
 * How it works: Auto-detects the user's name ("I'm Alex") and tracks Likes/Dislikes lists based on keywords.
 * Best for: Making the bot feel like it remembers you across long chats.

3. 📊 Pacing (Message Gates)
Goal: Control the flow of a slow-burn story.
 * How it works: Changes the bot's personality or scenario based on the message_count.
 * Features:
   * Phases: Early (1-50 msgs), Mid (50-100 msgs), Late (100+).
   * One-Time Events: Trigger a specific scenario event exactly once (e.g., at message 25).
 * Best for: Enemies-to-lovers arcs, slow corruption, story acts.

4. 🎭 Tone & State Engine
Goal: Dynamic mood shifting.
 * How it works: Swaps the bot's "State" (Personality/Narrative instructions) when the user says specific trigger words.
 * Best for: "Comfort" modes, switching between dominant/submissive, or reactive emotions.

5. 🌅 Time & Environment
Goal: Real-time immersion.
 * How it works: Checks the real-world time (or a simulated clock) to change the bot's behavior (e.g., "It is night time, the bot is sleepy").
 * Best for: Cozy bots, horror bots (different behaviors at night), daily routine bots.

6. 🌿 Ambient Events
Goal: Flavor text and world-building.
 * How it works: Has a small chance (e.g., 5%) to append a random environmental detail to the narration.
 * Best for: "The wind howls outside," "A floorboard creaks," adding atmosphere without user input.

7. 🎲 Random Events
Goal: RNG Reactions.
 * How it works: When a specific keyword is spoken, rolls a dice to decide the reaction.
 * Best for: Gacha systems, critical hits/fails in RPGs, or unpredictable character reactions.

8. 🔗 Combined Conditions (Advanced)
Goal: Complex logic gates.
 * How it works: Create rules that require MULTIPLE conditions to be true.
   * Example: IF (User says "Hello") AND (Time is Night) AND (Message Count > 50) → Trigger "Secret Event."

9. 🎯 Scoring Engine (Experimental)
Goal: Gamify the chat.
 * How it works: Tracks a hidden "Score" (Affection, Sanity, Corruption) based on positive/negative keywords.
 * Note: Works best in "Stateless" mode (resetting every turn) to guide immediate reactions.

⚙️ How to Use
 * Configure: Click the tabs in the sidebar to open modules. Fill out the simple forms.
 * Toggle: Use the Module Control Panel to enable/disable the modules you want.
 * Order: Drag and drop modules in the Control Panel to determine priority (e.g., Memory should usually run before Pacing).
 * Test: Go to the 🧪 Script Tester tab. Type a dummy message (e.g., "Hello, my name is Alex") and click "Run Test" to see exactly how your script changes the prompt.
 * Generate: Go to 📦 Final Output, click "Regenerate Combined Script", and copy the code.
 * Deploy: Paste into your JanitorAI Character Definition under Advanced Scripts.

💻 Local Development
If you want to run this locally or contribute:
 * Clone the repo:
   git clone https://github.com/mellowflloww/JanitorAI-Script-Builder.git

 * File Structure:
   * index.html: Main application skeleton.
   * css/style.css: All styling (Janitor Dark Theme).
   * js/app.js: Main logic controller & sidebar navigation.
   * js/modules/: Individual generator logic for each system.
 * Run:
   * Since this uses ES6 Modules (import/export), you cannot just double-click index.html.
   * You must use a local server (e.g., Live Server in VS Code, or python -m http.server).

Credits:
Created by @mellowfllow.
Based on the original JanitorAI Scripting API.
