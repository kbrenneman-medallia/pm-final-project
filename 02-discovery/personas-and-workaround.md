# Personas & Workaround Analysis

> Supporting file for `competitive-and-journey.md` (Module 2 · Lab 2). Personas drawn from the Product Health & Insights Summary (`product-health-summary.md`), and a step-by-step analysis of the primary persona's manual workaround.

**Problem Hook:** We must solve losing discovery-driven viewers to other apps by addressing the gap that they have to leave StreamLine to find new movies and TV shows.

## Notes on the Hook

- **"They have to leave" goes further than the evidence.** Nobody in the research says the app lacks titles worth discovering; one participant (UXR-01) says there are "15,000 titles." What they describe is giving up on the app's discovery, not having no option but to leave. The underlying gap is **trust and curation**, not a missing discovery feature.
- **Not every departure in the research is about discovery.** UXR-08 switched to YouTube because playback crashed (BUG-1042). That's a stability problem, and including it would overstate how much evidence supports the hook.
- **The evidence is qualitative and comes from a small number of participants.** Only one participant (UXR-04) clearly left for a competitor because of discovery. That's enough to support the hook as a hypothesis, but not as a measured problem.

---

## Persona 1: The Curation Defector (primary)

*Based on: UXR-04 (primary), UXR-02, UXR-10*

- **Role:** A long-time, discerning viewer who sees watching as a deliberate evening activity, not background noise.
- **Goal:** To be reliably pointed to a small number of high-quality, unexpected movies and shows they'll actually finish and enjoy.
- **Friction:** The recommendation engine treats one viewing as a fixed preference. Watching one action film produces three franchise sequels (UXR-02, BUG-1091), and the algorithm feels designed to keep them scrolling, not to help them choose (UXR-10). The breaking point is UXR-04: *"It became a warehouse... A competitor emails me two hand-picked films a week and I watch both."* This viewer didn't leave because they ran out of content. They left because someone else's curation earned their trust.

*Fit with the hook:* **Strong.** This is the clearest example of the hook: a viewer who left StreamLine for another service specifically to discover new things.

## Persona 2: The Overwhelmed Browser (secondary)

*Based on: UXR-01 (primary), UXR-12, UXR-09, UXR-07*

- **Role:** A committed, frequent viewer who opens the app wanting something new but has no clear title in mind.
- **Goal:** To quickly find a movie or show that suits their mood tonight, without having to know its name first.
- **Friction:** The app only helps users who already know what they want. A descriptive search like "slow quiet French drama" returns an action film (UXR-07, BUG-1080), and there's no way to browse by mood such as "quiet Sunday" (UXR-09). The moment it falls apart is UXR-01: *"I open the app, scroll for like twenty minutes, and close it without watching anything... I ended up going back to a DVD."* The focus group showed the same pattern, with participants saying the number of choices made them anxious (UXR-12).

*Fit with the hook:* **Moderate.** This viewer does leave the app, but for something familiar and offline, not for a rival discovery service.

**What both personas show:** Neither is short of content. Both are short of a guide they trust. The Curation Defector found that guide elsewhere. The Overwhelmed Browser gave up looking.

---

## Workaround Analysis: The Curation Defector

### What the Research Shows

The research describes three workarounds. It doesn't name any specific third-party apps, sites or newsletters.

| Workaround | Source | Evidence |
|---|---|---|
| A competitor's curated email: "two hand-picked films a week" | UXR-04 | Observed |
| Personal recommendations from friends, trusted over the algorithm | UXR-10 | Observed |
| Looking for a human curator, in place of the algorithm | UXR-02 | Observed (stated as a wish, not a current habit) |

Steps marked **Inferred** connect the workaround to known product behavior. They aren't directly reported by participants.

### The Workaround, Step by Step

1. **Stop trusting the in-app recommendations.** *(Observed: UXR-02, UXR-10)* After repeatedly getting near-duplicate suggestions (BUG-1091), the viewer stops treating the home screen as a place to discover things.
2. **Get picks from outside the app.** *(Observed: UXR-04, UXR-10)* Discovery happens through a friend's suggestion or a competitor's weekly email of hand-picked films, before the viewer opens StreamLine.
3. **Bring the title back into StreamLine by searching its exact name.** *(Inferred)* Search only works with exact titles (BUG-1080), so this works only because the outside source supplies the name. StreamLine is used to look up and play, not to discover.
4. **Save it for later, on whichever device is at hand.** *(Inferred, based on UXR-06)* "My List" doesn't sync to the TV (BUG-1058, 340+ tickets), so the save may disappear: *"So I never found it again."*
5. **Watch it, often across more than one sitting or device.** *(Inferred, based on BUG-1061)* The viewer may have to find their place again by hand because resume position isn't kept.
6. **Switch to the service that does the curating.** *(Observed: UXR-04)* The viewer sees that the curating service already provides what they value most, and cancels StreamLine.

### Why the Workaround Is Inefficient

- **The work moves to the viewer and the people around them.** Discovery depends on friends being available, or on an outside email's schedule. "Two films a week" is a hard limit StreamLine can't control.
- **Every step leaves the app.** Choosing, saving and returning happen in different places, and each switch is another chance to lose the title.
- **Getting the title back into StreamLine is unreliable.** The steps that bring an outside pick back are exactly where known Critical and High bugs occur (BUG-1058, BUG-1061).
- **StreamLine adds nothing.** At best, the app works as a search box plus a player.
- **The recommendation engine learns little.** *(Inferred)* The engine sees the viewing, but not why it happened.

### How the Workaround Feeds the Business Crisis

1. **Users come to trust whoever recommends titles, not whoever streams them.** Once the outside source also streams content (UXR-04), leaving StreamLine costs the viewer almost nothing.
2. **StreamLine becomes a content library people can easily replace.** It competes only on catalog size and price: the "warehouse" (UXR-04).
3. **The engine gets worse for the users who matter most.** *(Inferred)* With discovery happening elsewhere, the engine keeps falling back on franchise similarity for these viewers, deepening the self-reinforcing loop.
4. **Technical bugs confirm the decision to leave.** Sync and resume bugs hit the moment the viewer brings an outside pick back into StreamLine.
5. **Losing these viewers may cost word-of-mouth recommendations.** *(Inferred)* These discerning viewers are likely the "friends" others trust more than the algorithm (UXR-10).

### How Strong the Evidence Is

The full journey, from workaround to cancellation, is observed for only one participant (UXR-04). UXR-02 and UXR-10 support the attitudes behind it but don't show anyone leaving. Steps 3–5 are reasonable connections to documented bugs, not reported behavior.
