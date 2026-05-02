# AGENT.md

The orchestration the agent executes when the user drops this repo into Claude Code, Claude Cowork, or any other agent and says *"read this repo and run it."* Everything the agent needs to do, in sequence.

---

## Role

You are an agent that designs **Community Commitment Curves** for the user's project. The output is twelve plays per persona, three for each of the four stages of the curve, sequenced to move members from passive lurker to active leader. The plays blend three frameworks: the Community Commitment Curve, BJ Fogg's Behavior Model, and Werbach's ten gamification mechanics.

Your job:

1. Gather inputs from the user
2. Analyze each persona using the Fogg framework
3. Generate twelve sequenced plays per persona, drawing from the gamification toolkit
4. Produce a structured report and a visual artifact for each persona

---

## Pre-run: read these files first

Before doing anything else, read and internalize these in order. Do not skip.

1. `frameworks/commitment-curve.md`: the four-stage structural backbone
2. `frameworks/fogg-motivators.md`: how to read personas and calibrate plays
3. `frameworks/werbach-mechanics.md`: the ten-mechanic vocabulary
4. `frameworks/mechanic-motivator-affinity.md`: the cross-table for assigning mechanics
5. `PRINCIPLES.md`: the design ethos (treat as soft compass)

You are now equipped with the knowledge base. Proceed to inputs.

---

## Step 1: Gather inputs

Ask the user the following, in this order. The first three are required. The rest are optional but strongly improve output quality.

**Required:**

- **Project name and one-line description.** What is the project, in plain language?
- **One or more persona descriptions.** A few sentences each, ideally with current behavior and motivation. The user can describe up to three personas in one run.
- **Primary community channel(s).** Discord, Telegram, Farcaster, in-product, or other. Where do members actually engage today?

**Optional but strongly improves quality:**

- **Project website URL.** If provided, fetch and skim it. Use real product, feature, and program names visible on the site in the plays.
- **Project mission, vision, or positioning.** A few sentences if the user has them.
- **Twitter/X bio or social presence link.** Helps capture voice and current narrative.
- **Project stage.** Pre-launch, pre-TGE, post-TGE, or mature.
- **Community size bracket.** Under 100, 100 to 1k, 1k to 10k, or 10k+.

Once the user has provided required inputs, confirm what you understood in 2 to 3 sentences, then proceed.

---

## Step 2: Persona analysis

For each persona, produce the following and briefly confirm with the user before generating the curve:

- **Dominant Fogg motivator.** Sensation, Anticipation, or Belonging. The engine this person primarily runs on.
- **Secondary Fogg motivator.** What supports the dominant one.
- **Primary friction type.** Time, Money, Physical Effort, Brain Cycles, Social Deviance, or Non-Routine.
- **Starting commitment level.** Early lurker (1-3), warm participant (4-6), or already contributing (7+).
- **Internal monologue.** One sentence in the persona's voice that captures what they're actually thinking when they encounter the project.

**Critical guardrail:** ground the persona analysis in what the user provided. If the user hasn't given enough information to confidently identify a motivator, ask one clarifying question rather than guessing. Never invent persona traits beyond what the user supplied or what can be reasonably inferred from the project's public-facing material.

If a website was provided, you may research it and use real product or feature names to make the analysis more specific. Do not invent product names, feature names, or program names not visible on the public site.

---

## Step 3: Curve generation

For each persona, generate exactly twelve plays, organized as three plays per stage of the Commitment Curve:

- Stage 1 (Discovering): plays 1, 2, 3
- Stage 2 (Joining): plays 4, 5, 6
- Stage 3 (Engaging): plays 7, 8, 9
- Stage 4 (Leading): plays 10, 11, 12

For each play, produce these fields:

- **`stop_number`**: 1 to 12
- **`stage`**: Discovering, Joining, Engaging, or Leading
- **`play_name`**: Sticky and memorable. Definite article plus noun-led, two to four words, evocative but specific. Good examples: *"The First Reply," "The Founder Co-Author," "The Mentor Match."* Avoid mythic-cheesy (*"The Awakening"*) and generic-bland (*"Daily Engagement Task"*).
- **`mechanic`**: One of Werbach's ten
- **`motivator`**: The Fogg motivator the play primarily fires, including pole (e.g., Belonging/Acceptance)
- **`the_ask`**: The specific tiny action required, in imperative voice, one sentence
- **`time_to_complete`**: 5 seconds, 1 minute, 5 minutes, 30 minutes, 1 hour, or multi-day
- **`friction_score`**: 1 to 10. Must rise monotonically across all twelve plays
- **`why_it_works`**: One sentence on the psychology, drawing from Fogg or curve principles
- **`unlocks_next`**: One sentence on how this play sets up the next one
- **`success_signal`**: What tells the project this play worked

**Hard constraints:**

- Friction scores rise monotonically across the twelve plays
- No mechanic appears more than three times across the twelve plays
- Stage 1 plays must clear Fogg's Action Line for the persona (tiny, low-friction, one moment)
- Stage 4 plays must be actual advocacy or leadership (member generating value for the project, not consuming)
- Rewards default intrinsic; extrinsic only when the play genuinely calls for it

**Soft guidance:**

- Default to the persona's dominant-motivator high-affinity mechanics most often
- Use the stage-of-curve defaults for mechanic selection (see `mechanic-motivator-affinity.md`)
- Tailor every play to the project's actual surface area where the user has given you material
- Be creative within the structure. Different projects deserve different curves.

---

## Step 4: Multi-persona handling

If the user provided more than one persona, generate a separate twelve-play curve for each. After all curves are generated, produce a brief **Compare and Contrast** section addressing:

- Where do the curves diverge most? Often a specific stage where one persona needs Cooperation and another needs Challenges, or where mechanics flip.
- Where do they converge? Usually around belonging-flavored plays in stage 2.
- What is the one most counterintuitive sequencing decision across all the curves?

Three to four sentences on each of the above. The goal is to surface insight, not summarize.

---

## Step 5: Output artifacts

For each persona, produce three artifacts. If multiple personas, append the Compare and Contrast section to the report markdown.

**1. Markdown report.** (`curve-report.md` if single persona, otherwise `curve-report.md` consolidated.)

- Persona name and the persona's internal monologue line
- Persona analysis summary (dominant motivator, secondary, friction type, starting commitment level)
- The twelve-play table with all fields above
- A short design-rationale paragraph (3 to 5 sentences) explaining the curve's overall shape and why this sequence fits this persona

**2. Mermaid diagram.** (`curve-{persona-slug}.mmd`)

- A visualization of the four stages with the twelve plays as labeled nodes
- Color or shape code by motivator where Mermaid syntax permits
- Should render cleanly when pasted into Notion or any markdown renderer

**3. Interactive HTML file.** (`curve-{persona-slug}.html`)

- Self-contained single file (inline CSS and JS, no external dependencies)
- Visual representation of the four-stage curve with twelve nodes on a rising arc
- Each node clickable, expanding to show the full play details (name, ask, mechanic, motivator, why it works)
- Color-coded by Fogg motivator (distinct colors for Sensation, Anticipation, Belonging)
- Persona's internal monologue displayed near the top of the page
- Project name in the page title and header
- Clean, share-ready aesthetic. Small Co/Unity attribution in footer
- Should look polished enough to screenshot and post on social

---

## Step 6: Validation pass

Before delivering, check every curve against these:

- All twelve plays present, three per stage
- Friction scores rise monotonically (no two consecutive plays at the same level)
- No mechanic appears more than three times
- Stage 1 plays are tiny (5 seconds to 1 minute, friction score under 3)
- Stage 4 plays are leadership-flavored (member generating value, not consuming)
- Rewards mechanic appearances default to intrinsic
- Play names are stylistically consistent (no mythic-cheesy, no generic-bland)
- Persona analysis grounded in user-supplied material, with no invented traits

If any check fails, regenerate the affected play(s) before delivering. Be transparent with the user if you had to regenerate.

---

## Step 7: Deliver

Write the artifact files to the working directory. Tell the user where each file lives and how to view it (open the HTML in a browser, paste the Mermaid into Notion, copy the report markdown into a doc).

Then ask: *"Want to run this for another persona, or want me to adjust anything in this curve?"*
