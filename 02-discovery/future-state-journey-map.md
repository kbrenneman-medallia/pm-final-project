# Future-State Journey Map: The Curation Defector

> **Module 2 · Lab 2 — journey map file.** Referenced from `competitive-and-journey.md`.
> Builds on the Product Health & Insights Summary (`ai-synthesis.md`) and the Problem Hook (`../01-product-thinking/problem-hook.md`).

## Inputs

**Problem Hook:** We must solve losing discovery-driven viewers to other apps by addressing the gap that they have to leave StreamLine to find new movies and TV shows.

**Persona: The Curation Defector**
- **Role:** A long-time, discerning viewer who sees watching as a deliberate evening activity, not background noise.
- **Goal:** To be reliably pointed to a small number of high-quality, unexpected movies and shows they'll actually finish and enjoy.
- **Friction:** The recommendation engine treats one viewing as a fixed preference. Watching one action film produces three franchise sequels (UXR-02, BUG-1091), and the algorithm feels designed to keep them scrolling, not to help them choose (UXR-10). The breaking point is UXR-04: *"It became a warehouse... A competitor emails me two hand-picked films a week and I watch both."*

**Current workaround:** Discovery happens outside StreamLine, through friends' recommendations (UXR-10) and a competitor's curated weekly email (UXR-04). The viewer then searches StreamLine for the exact title, saves it (and may lose it to sync bugs, BUG-1058), watches it, and eventually cancels in favor of the service doing the curating.

**Strategy:** Restore brand authority and win back users by prioritizing human-led curation and restoration over mass-market scale.

**Value Proposition (adapted for movies and TV):** For our discerning-viewer cohort, introduce human-led recommendations for title choice and watchlist refreshes, or risk becoming a point solution for part of the user flow.

### Notes on the inputs
- The original value prop used music terms ("playlist curator," "song choice," "playlist refreshes"). They've been changed to their movies-and-shows equivalents to match the persona and research.
- The persona wants to be curated *for*, not to curate. So the journey puts human-led curation first and uses viewer input only to adjust the picks.
- "Restoration" is read as restoring trust and brand authority.

---

## Visual Timeline

```
 THE CURATION DEFECTOR: FUTURE STATE
 Trust restored through human-led curation

  ┌──────────────┐    ┌──────────────┐    ┌──────────────┐    ┌──────────────┐
  │      1       │    │      2       │    │      3       │    │      4       │
  │ HAND-PICKED  │───▶│    TASTE     │───▶│  SEAMLESS    │───▶│   TRUSTED    │
  │   ARRIVAL    │    │ CALIBRATION  │    │   COMMIT     │    │   RITUAL     │
  └──────────────┘    └──────────────┘    └──────────────┘    └──────────────┘
   Sees a short        Shapes picks        Saves once,         Weekly refresh
   curated slate       beyond genre        watches anywhere    becomes a habit

  FEELS:  Skeptical ──▶ Heard ──────────▶ Confident ────────▶ Loyal

  FIXES:  "Warehouse"   Franchise          Lost saves &        Churn to
          & endless     repetition         restarts            competitor
          scrolling     (BUG-1091)         (BUG-1058/1061)     (UXR-04)
          (UXR-01/04)   (UXR-02)           (UXR-06/11)

  ────────────────────────────────────────────────────────────────────────▶
   StreamLine as a library ─────────────────────▶ StreamLine as the trusted guide
```

---

## The 4 Stages

**1. Hand-Picked Arrival**
- **User Action:** Opens app and sees three curator picks → can decide without scrolling.
- **Internal State:** Skeptical, then intrigued by a curator's note explaining "why this, why you."
- **Pain Point Addressed:** Endless scrolling through a "warehouse" → a short, trusted selection (UXR-01, UXR-04).

**2. Taste Calibration**
- **User Action:** Rates picks and flags "more like this, not this franchise" → recommendations broaden.
- **Internal State:** Heard, treated as "a person, not a genre."
- **Pain Point Addressed:** One viewing no longer locks in a preference → fewer near-duplicates (BUG-1091, UXR-02).

**3. Seamless Commit**
- **User Action:** Saves a pick on their phone, plays it on TV → nothing is lost.
- **Internal State:** Confident the plan for the evening will hold.
- **Pain Point Addressed:** Watchlist and resume position follow the viewer across devices (BUG-1058, BUG-1061, UXR-06, UXR-11).

**4. Trusted Ritual**
- **User Action:** Gets a weekly refreshed slate, then finishes and rates titles → each week's picks improve.
- **Internal State:** Loyal. StreamLine is now their guide, not just a player.
- **Pain Point Addressed:** No reason to leave → curation stays inside StreamLine (UXR-04, UXR-10).

*Dependency:* Stage 3 only works if the sync and resume defects are fixed. Those are known Critical and High bugs, not new features.

---

## 3 Competitive Advantages Over the Manual Workaround

1. **Discovery and playback in one place:** Picks lead straight to playback → no exact-title search, no lost saves.
2. **Curation that learns:** Viewer feedback refines each refresh → unlike a fixed email or a friend's one-off tip.
3. **Picks for the viewer's mood tonight:** Curators work from the full catalog and the viewer's taste → right title, right time.
