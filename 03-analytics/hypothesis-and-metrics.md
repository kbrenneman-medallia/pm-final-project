# Hypothesis & Success Metrics

> **Module 3 · ★ Deliverable 3.** Repo file `03-analytics/hypothesis-and-metrics.md` — part of your submission.
> It feeds the **Problem, Value & Hypothesis** slide of your Module 6 final deck.

## Finalized product hypothesis

> Based on viewers reporting that they scroll for twenty minutes and give up (UXR-01, UXR-12), and on Spotlight cohorts cutting churn by 22 pts for Wanderers and 14 pts for Casual Browsers, I believe that **reducing the time it takes to find something worth watching** for **Wanderers and Casual Browsers** (78% of the base) will result in **more titles started and finished, and more viewers returning the next month**, as measured by a **25% reduction in median browse time before first play** (a proposed target). I will protect **Power User churn and LTV ($14.20)** and make a go/no-go decision after **90 days (three monthly renewal cycles)**.

## Success metrics

| Metric | Type | Target | Why it matters |
|---|---|---|---|
| Mo. 0→1 retention, Wanderers + Casual Browsers | North-star | Close the gap from Full Library (63%) toward Spotlight cohorts (74–79%) | Ties the initiative to renewal and churn, the business outcome behind the Problem Hook |
| Median browse time before first play (session open → play) | Leading indicator | −25% vs. control (proposed) | Measures the friction directly: the scrolling that ends with no choice and a closed app |
| Browse-to-play conversion + 30-min completion | Leading indicator (quality check) | No decline; ideally both rise | Stops shorter browse time from being read as success when viewers are really giving up sooner or starting poor picks |
| Power User churn and LTV | Guardrail | Churn flat; LTV ≥ $14.20 | Protects the highest-value segment, which relies on the curated mix (58%) |

**Notes on the targets**
- The −25% target is a proposed starting point, not derived from a baseline. Set it once the current median browse time is pulled for each segment.
- A 90-day window assumes monthly billing. If a large share of subscribers pay annually, three "renewals" won't happen in 90 days, so use Mo. 0→1 and Mo. 1→2 retention as the renewal proxy.
- **Go:** browse time falls, conversion and completion hold or rise, Mo. 1 retention improves, and the Power User guardrail holds. **Pivot:** browse time falls but completion drops (we're surfacing the wrong titles). **Kill:** no movement in browse time or retention after 90 days.

---

## Pre-work · Hypothesis check

- **Role (from M2):** A long-time, discerning viewer who sees watching as a deliberate evening activity, not background noise.
- **Goal:** To be reliably pointed to a small number of high-quality, unexpected movies and shows they'll actually finish and enjoy.
- **Friction / moment of misery:** The recommendation engine treats one viewing as a fixed preference. Watching one action film produces three franchise sequels (UXR-02, BUG-1091), and the algorithm feels designed to keep them scrolling, not to help them choose (UXR-10). The breaking point is UXR-04: "It became a warehouse... A competitor emails me two hand-picked films a week and I watch both." This viewer didn't leave because they ran out of content. They left because someone else's curation earned their trust.
- **Current workaround (M2):** A competitor's weekly email with two hand-picked films, recommendations from friends, and a wish for a human curator in place of the algorithm.
- **Problem Hook (M1):** We must solve losing discovery-driven watchers to other apps by addressing the gap that they have to leave StreamLine to find new programs.
- **Value Proposition (M1):** For our heavy playlist curator cohort, introduce recommendation tools for program choice and playlist refreshes or risk becoming a point solution for part of the user flow.

## Read your data snapshots

- **Funnel vs. M2 friction:** The M2 problem was finding something interesting to watch instead of scrolling endlessly. In aggregate, the funnel doesn't show adoption or success improving on any metric, even with Spotlight in use, but the data can't be split by Spotlight users vs. non-users, so the aggregate may hide the effect. More data is needed to explain the drop-off between starting a title and the 30-minute mark: content quality, autoplay/next-up, load issues, or Spotlight changing behavior.
- **Retention vs. workaround:** Yes, the patterns largely align. The persona gets picks from outside the app and uses StreamLine only to look up exact titles, so they have little reason to stay engaged early. That matches the large, worsening Mo. 0→1 drop in the Full Library cohorts (e.g., Nov: 63% at Mo. 1) and the falling search-then-play rate. Spotlight cohorts retain better (74–79% at Mo. 1), which suggests in-app curation fills the gap the persona fills elsewhere. Caveats: the heatmap covers new subscribers, not long-tenured viewers, and watching across multiple sittings and devices could shorten sessions without meaning disengagement. Check whether Spotlight retention holds up among veteran users.
- **LTV gap and content mix:** The M2 persona is closest to the Power User segment: a high-intent viewer who relies on curation (58% curated mix) but has lost trust in the app's picks. The data partly confirms this, since a curation failure would hit this group hardest, but it doesn't show their pain: Power Users have low churn and the highest LTV ($14.20). The misery in the 61% trending mix belongs to Wanderers. Wanderers and Casual Browsers are 78% of the base and show the largest churn reduction from Spotlight (22 and 14 pts), so the initiative is retargeted to them (see below).
- **Low adoption / scheduling (42%):** N/A — this prompt is for the RouteLogic track.
- **Workflow data vs. manual process:** N/A — this prompt is for the RouteLogic track.
- **CSAT heatmap / NPS trend:** Not completed.

## Step 3 · Craft your hypothesis

- **Qualitative evidence (M2):** Every step of the workaround leaves the app or depends on the viewer and the people or services around them. Getting a title back into StreamLine is unreliable (exact-title search only, BUG-1080), and the recommendation engine isn't learning (BUG-1091). For the browsing segment: "I open the app, scroll for like twenty minutes, and close it without watching anything" (UXR-01), and the number of choices made focus-group participants anxious (UXR-12).
- **Quantitative evidence (M3):** Wanderers and Casual Browsers are 78% of the base; Spotlight reduced their churn by 22 and 14 pts respectively. Wanderers' content mix is 61% trending. Full Library Mo. 1 retention is 63% (Nov) vs. 74–79% for Spotlight cohorts.
- **Persona:** Wanderers and Casual Browsers, matching the M2 secondary persona (the Overwhelmed Browser): frequent viewers who open the app without a title in mind and give up after scrolling.
- **Problem:** Wanderers and Casual Browsers can't quickly find something good to watch, so they scroll, give up, and close the app.
- **Strategic outcome:** Viewers shown good content will choose it, watch it, stay in the app and come back, rather than wasting time scanning. That shows up as lower churn and higher Mo. 1 retention.
- **Primary success metric:** Median browse time before first play.
- **Guardrail metric:** Power User churn and LTV must not decline while the focus shifts to the other two segments.
- **Decision window:** 90 days, roughly three monthly renewal cycles for viewers to judge whether the product is worth keeping.

## Open questions

- Persona shift: the M1 Value Proposition targets the "heavy playlist curator cohort" (closest to Power Users). Now that the hypothesis targets Wanderers and Casual Browsers, update the Value Proposition in `01-product-thinking/problem-hook.md` to match before the final deck.
- Need Spotlight vs. non-Spotlight segmentation in the funnel to attribute any change to the initiative.
