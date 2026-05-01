# Mechanic × Motivator Affinity

The cross-table that guides which gamification mechanic best fires which Fogg motivator. The agent uses this when assigning mechanics to plays, after it has identified the persona's dominant motivator from `fogg-motivators.md`.

The affinities here are defaults, not laws. The agent should treat them as strong guidance and override only when the project context or the persona's secondary motivator makes a different choice clearly better.

---

## The affinity table

How well each Werbach mechanic fires each Fogg motivator.

| Mechanic | Sensation | Anticipation | Belonging |
|---|---|---|---|
| Challenges | **High** | Medium | Low |
| Chance | **High** | **High** | Low |
| Competition | Medium | Medium | Low |
| Cooperation | Low | Medium | **High** |
| Feedback | Medium | Medium | **High** |
| Resources | Low | **High** | Medium |
| Rewards (intrinsic) | Medium | **High** | **High** |
| Transaction | Medium | Medium | Low |
| Turns | Low | **High** | Medium |
| Win States | Medium | **High** | **High** |

*Affinity ratings for Rewards reflect intrinsic flavor (recognition, status, access). Extrinsic-flavored rewards score lower across all three motivators in a community context and should be deployed sparingly per the guidance in `werbach-mechanics.md`.*

---

## Rules of thumb by dominant motivator

Once the agent has identified the persona's dominant motivator, default to mechanics in the **High** column for that motivator.

- **Belonging-dominant persona.** Cooperation, Feedback, Win States, Rewards (intrinsic, recognition-flavored). The plays should make the member feel seen and chosen.
- **Anticipation-dominant persona.** Resources, Turns, Win States, Rewards (intrinsic, access-flavored). Add Chance for surprise upside. The plays should reveal what's next and make the future feel earned.
- **Sensation-dominant persona.** Challenges, Chance, Competition. The plays should feel good in the act of doing them.

Most personas mix two motivators. Use the dominant motivator for primary mechanic choice, and fold the secondary motivator's mechanics in as supporting plays across the twelve.

---

## Rules of thumb by stage of the curve

The mechanic vocabulary also shifts depending on where in the curve a play sits.

- **Stage 1, Discovering.** Low-friction, low-stakes. Default to Feedback (something visibly responds to the member's attention) and Chance (low-effort surprise). The member is browsing.
- **Stage 2, Joining.** First explicit ask, must be tiny. Default to Feedback (welcome reactions, recognition by name) and Cooperation in light forms (one-emoji reactions on someone else's post). Belonging-flavored mechanics tend to be right here regardless of the persona's dominant motivator, because earning a sense of belonging is the unlock for the rest of the curve.
- **Stage 3, Engaging.** Recurring participation. Default to Cooperation (small group work), Challenges (sized for skill level), and Turns (rotational features, member spotlights). The member is investing.
- **Stage 4, Leading.** Ownership and identity shift. Default to Win States (graduations, role grants, public recognition), Resources (privileged access), and Cooperation (co-design, member-led initiatives).

---

## How the agent uses this file

After identifying the persona's dominant and secondary motivators, and after deciding which stage of the curve a play sits in:

1. Find the dominant motivator's **High** mechanics in the affinity table
2. Cross-reference against the stage-of-curve defaults above
3. When the persona's affinity and the stage default don't fully overlap, prefer mechanics that satisfy both. The agent has three plays per stage; not every play needs to maximally fire the dominant motivator
4. Don't repeat the same mechanic more than three times across the twelve plays of one curve
5. When the play uses Rewards, default intrinsic. Reach for extrinsic only when the moment genuinely calls for it
