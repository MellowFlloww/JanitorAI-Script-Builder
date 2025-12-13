# JanitorAI Script Builder (BETA 2)

**Live tools (GitHub Pages):**

**Main generator (BETA 2):** https://mellowflloww.github.io/JanitorAI-Script-Builder/

No-code advanced scripts for JanitorAI.
Fill out simple forms → get copy-paste-ready JavaScript. No JS knowledge needed.


---

**What this actually does**

JanitorAI advanced scripts run after every message and can modify:

context.character.personality — how the bot tends to speak/act

context.character.scenario — extra “hidden narration” and behavior notes


These tools just generate those scripts for you.

You tell the form what you want to happen, the page turns that into JavaScript.
You don’t need to touch or understand the code — just paste it into your bot.


---

**How to use (TL;DR)**

1. Open one of the links above.


2. Pick a tab / module (Memory, Pacing, Tone / State, Random Events, etc).


3. Fill in the fields like you’re describing your character’s behavior.


4. Click Generate Script.


5. Copy the code block at the bottom.


6. In JanitorAI, go to your character → Scripts → create an Advanced Script → paste.


7. Test in a private chat. If something feels off, tweak the form and regenerate.



You can use one module or several together in the same character —
just paste each generated script into its own advanced-script slot.


---

**Modules (simple explanation)**

**1. Memory Script Generator**

Goal: fake “remembering” user details.

Detects phrases like *“my name is Alex”* and adds a small memory note: *“Remember: the user’s name is Alex.”*

Lets you list likes/dislikes (comma-separated).

Likes → “remembers the user likes X”

Dislikes → “avoids mentioning X”


Optional generic trait: “seems to remember details from earlier.”


Good for: basic continuity without writing regex or logic.


---

**2. Pacing Script Generator**

Goal: early / mid / late-game versions of your character.

Uses context.chat.message_count to decide which “phase” you’re in.

You configure:

Phases

Start/end message range (ex. 1–10, 11–30, 31+)

Personality note for that phase

Scenario / atmosphere note for that phase


Optional one-time events

Fires exactly once at a specific message count

Adds a short scenario beat



Good for: slowburns, characters who open up over time, plot “acts.”


---

**3. Tone / State Engine Builder**

Goal: flip moods based on what the user says.

You define states like:

Name: protective, comforting, furious, flirty, etc.

Trigger phrases (comma-separated, case-insensitive)

Personality + scenario add-ons for that tone


When a trigger appears in the last user message, the script swaps tone and adds your notes.

Good for: omegaverse toggles, comfort mode, “angry route,” etc.


---

**4. Random Event / Weighted Reaction Builder**

Goal: “this only happens sometimes.”

You set:

One trigger phrase (ex. *“i love you”*)

Several reactions with numeric weights


Every time the trigger appears, the script:

1. Rolls a random number


2. Picks exactly one reaction (higher weight = more common)


3. Appends reaction text to context.character.scenario



Good for: rare events, subtle variety, RNG drama.


---

**Relationship / “Slowburn” Builder**

relationship-builder.html is a pre-packaged setup focused on relationship progress:

Memory hooks for affection/preferences

Pacing phases for masks dropping over time

Optional tone flips for confessions / fights

Optional random spikes of behavior


It uses the same ideas as the main tool, but the wording/fields are tuned for romance/slowburn arcs.


---

**Notes / Safety**

Everything runs client-side only. Nothing is stored or sent anywhere but your browser.

You can open the generated code to see exactly what it does.

If something breaks, delete that script in JanitorAI and regenerate from the page.



---

**Quick Examples**

**Example 1 — Yandere slowburn (masks dropping over time)**

Goal: Start sweet → slowly clingy → openly yandere.
Where: Pacing module.

**1. Phase 1 – Sweet / safe**

Start: 1

End: 15

Personality note:
Warm, affectionate and wholesome; hides darker thoughts behind easy smiles.

Scenario note:
Cozy, safe atmosphere. Gives you space, responds gently, seems genuinely kind.



**2. Phase 2 – Clingy / cracks in the mask**

Start: 16

End: 40

Personality:
More anxious and jealous. Subtle guilt-trips, apologizes too quickly.

Scenario:
Checks in constantly. Smiles feel a bit too fixed. Mood turns tense under sweetness.



**3. Phase 3 – Full yandere**

Start: 41

End: (leave empty)

Personality:
Drops the act. Possessive, obsessive, treats everyone else as a threat.

Scenario:
Heavy atmosphere. Uses remembered details to keep you close.



**4. Optional one-time events**

Fires at 25:
They casually slip they’ve been following your habits, then laugh it off.

Fires at 60:
They calmly admit they can’t stand losing you, no matter what it takes.




Generate → paste into advanced scripts.


---

**Example 2 — Comfort bot that reacts to sadness**

Goal: When user expresses sadness, bot shifts into comfort mode.
Where: Tone / State.

State name: comforting

Triggers:
i feel sad, i'm sad, i feel down, i'm lonely, i'm tired of everything

Personality add-on:
Much softer and more patient, focused on grounding and reassurance.

Scenario add-on:
Atmosphere softens; voice feels warm and steady.


Generate → paste.


---

**Example 3 — Rare “big reaction” chance**

Goal: Normal reaction 95% of time, dramatic 5%.
Where: Random Events.

Trigger: i love you

Reactions:

Weight 95:
They smile, flustered but happy, replying gently.

Weight 5:
They freeze, then reply intensely, like they’ve waited forever.



Generate → paste.


---

*These examples mix well with the Memory module to add “fake relationship memory” on top.*
