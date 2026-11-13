# Product Health & Insights Summary

> Supporting file for `ai-synthesis.md` (Module 2 · Lab 1). Full AI synthesis output, plus a technical drill-down on Algorithmic Curation & Trust.

**Sources:** 12 user research sessions (UXR-01 to UXR-12) and 10 bug reports (BUG-1042 to BUG-1121). Participants are referred to by research ID only.

---

## Executive Summary

The product's core is fragile in specific places. Playback failures on Smart TVs and broken sync between devices are directly causing users to abandon sessions and switch to competitors. The bigger long-term risk is not technical, though: users consistently describe a large catalog that feels overwhelming, recommendations they find repetitive and don't trust, and no good way to browse for what they're in the mood for. Even if every technical defect were fixed, the experience would still lose engagement, because the product shows users more content but doesn't help them choose what to watch.

---

## Thematic Synthesis

### 1. Technical Stability & Performance

The playback failures are few but serious, and they are concentrated on Smart TVs, the main living-room screen. The most severe one turns a loading delay into a forced exit to the home screen. Users don't wait or retry; they leave the app (UXR-08, BUG-1042). Slow startup on older TVs adds to the sense that the app is unreliable before playback even begins.

- **Playback ejects to home screen after ~60s of buffering (Samsung Tizen 2021+), reproducing 7 times out of 10.** Interviews confirm users switch directly to a competing app. **High**
- **Cold start averages 11s on older TV hardware.** Users see the app as "slow to open," which hurts first impressions at the start of every session. **Medium**

### 2. Cross-Platform Sync & Continuity

This is the most urgent technical area. Users move between phone, tablet and TV and expect their activity to follow them. Today it doesn't. Saved titles and playback progress stay on the device where they were created. The interviews show the result: users don't search again for what they lost, so the title is never watched or finished (UXR-06, UXR-11). The support ticket volume shows this is a widespread problem, not a few isolated cases.

- **"My List" does not sync between mobile and TV.** 340+ support tickets this quarter, and saved titles are lost for good from the user's point of view. **Critical**
- **Resume position is not kept across devices, so titles restart at 0:00.** This is the top driver of "couldn't finish" complaints and directly lowers completion rates. **High**

### 3. Discovery & Information Architecture

Users describe the catalog as a "warehouse." There is a lot of content, but it is hard to navigate by anything except exact title. Search can't handle descriptive or natural-language queries, and the home screen offers no way to browse by mood, occasion or tone. The result is decision paralysis: long scrolling sessions that end with nothing watched, retreat to familiar comfort titles, or anxiety about too many choices (UXR-01, UXR-03, UXR-09, UXR-12). The autoplay trailer adds sensory overload, enough that some users mute their TV entirely (UXR-05).

- **Choice overload and decision paralysis.** Users report scrolling for 20+ minutes without watching anything, and older users describe the volume of options as stressful. This is linked to cancellation (UXR-04) and to users going back to physical media. **Critical**
- **No browsing by mood or context.** Users can't find content for intents like "quiet Sunday" or "book club pick," and the home screen is described as uniformly "loud and new." **High**
- **Search only matches exact titles.** Descriptive queries return irrelevant results (e.g., "slow quiet French drama" returns an action franchise title). Rated Medium in the bug tracker, but it undercuts the main fallback for users the recommendations fail. **High**
- **Autoplay trailers play at full volume, ignore the user's volume setting, and can't be turned off.** Repeated triggers within one session, plus no opt-out, are pushing users to mute or leave the app. **Medium**

### 4. Algorithmic Curation & Trust

The recommendation engine has a credibility problem, not just a precision problem. "Because you watched" leans heavily on franchise and genre similarity, so users get near-duplicates and feel reduced to a single viewing event (UXR-02, BUG-1091). Several participants see the algorithm as serving engagement rather than their own goals (UXR-10). Many say they prefer human curation, from friends or from a competitor's small hand-picked weekly selection (UXR-02, UXR-04, UXR-12). Users value fewer, higher-confidence suggestions over endless volume.

- **"Because you watched" recommends low-variety, same-franchise titles.** Users call it "repetitive," and it surfaces no hidden gems. **High**
- **Users don't trust the algorithm's intent.** It is seen as built to keep them scrolling rather than to help them find something good, so they rely on outside sources like friends. **High**
- **Users want curated, human-style picks that the product doesn't offer.** A competitor's model of two hand-picked films a week was cited as the reason a user cancelled and moved over. **High**

---

**Minor Technical Debt:** Subtitles drift ~2s out of sync on titles longer than 90 minutes, intermittently (BUG-1099). Cover-art thumbnails show grey placeholders on slow connections (BUG-1104). The Continue Watching row keeps finished titles for up to 48 hours (BUG-1121). All three are **Low**.

**Severity note:** Ratings mostly follow the bug tracker. Two items are rated above their tracker rating because the interview evidence points to more user impact: choice overload is Critical because it is linked to cancellation, and search is High because it is the fallback when recommendations fail.

---

## Drill-Down: Algorithmic Curation & Trust (Technical Evidence)

### Scope and Evidence Base

There is little direct technical evidence for this theme. Only one bug report, **BUG-1091**, is about the recommendation engine itself. Several other bugs affect the data the engine relies on, or the screens where recommendations appear. Six research sessions (UXR-02, 03, 04, 09, 10, 12) describe the effects users experience.

Each finding is marked as one of two types:
- **Observed:** stated directly in a bug report or interview.
- **Inferred:** a likely technical cause that fits the evidence but hasn't been checked against the system's design or code.

### 1. Recommendations Are Too Narrow

**Observed:** BUG-1091 (Sev: High) says "Because you watched" recommends near-duplicate titles from the same franchise. Users call it "repetitive." UXR-02 gives a specific case: watching one action film produced three action-sequel recommendations.

**Inferred:** This pattern suggests the engine matches titles mainly on franchise and genre labels. It also seems to give a single viewing a lot of weight, and nothing in the evidence suggests a step that adds variety to the results. The bug report has no reproduction rate, ticket count or examples, so we can't tell whether this happens everywhere or only for certain genres.

- **Franchise and genre similarity dominates the "Because you watched" results.** **High**
- **The scale of the problem is unknown.** BUG-1091 has no repro rate or volume, unlike the sync and playback bugs. **Medium** (an evidence gap, not a product defect)

### 2. Title Descriptions Are Too Thin

**Observed:** BUG-1080 says search only works for exact titles. UXR-07 searched "slow quiet French drama" and got an action franchise title. UXR-09 asked for mood-based browsing ("quiet Sunday," "book club") that the product doesn't have.

**Inferred:** Search and recommendations probably have the same root problem: titles aren't described in enough detail. If titles are tagged mainly by genre and franchise, and not by tone, pace, language or setting, then search can't match descriptive queries and the recommendation engine can't find titles that are similar in feel but different in genre. The search result in UXR-07 didn't even match the query's genre, which suggests a fallback to popularity or keyword matching, not a near miss on meaning.

- **Titles can't be matched on tone, mood or style, which limits both search and recommendations.** **High**
- **Search for descriptive queries returns popular or loosely matched titles, not relevant ones.** **High**

### 3. Unreliable Viewing Data

**Observed:**
- BUG-1058 (Critical): "My List" doesn't sync across devices; 340+ tickets.
- BUG-1061 (High): resume position isn't kept across devices.
- BUG-1121 (Low): finished titles stay in Continue Watching for up to 48 hours.

**Inferred:** These are logged as sync defects, but they also suggest the user profile isn't kept as one up-to-date record. If the recommendation engine reads the same data:
- A title saved on one device never becomes a signal of interest on the others.
- A partly watched title may look like a drop-off on one device and a fresh start on another, which distorts completion signals.
- The 48-hour delay in BUG-1121 suggests completion status is updated in slow batches, so recommendations built on that data would lag behind what the user actually did.

The evidence doesn't show whether the recommendation engine uses these data sources. That link is the main unverified dependency in this analysis.

- **Viewing history may be split by device, so recommendations would work from partial data.** **High** (if confirmed)
- **Completion status lags by up to 48 hours, which could make recommendation signals stale.** **Medium**

### 4. A Self-Reinforcing Loop

**Observed:** UXR-03 describes rewatching four comfort shows. UXR-01 describes 20-minute browsing sessions that end without watching anything. BUG-1077 shows autoplay trailers that ignore the user's volume setting and can't be turned off. UXR-10 says the algorithm "just wants me to keep scrolling."

**Inferred:** The loop runs like this:
1. Narrow recommendations make it hard to discover new titles.
2. Users fall back on rewatching or leave without watching anything.
3. Rewatches are strong, repeated signals, and abandoned sessions leave no signal at all, so the engine's inputs get narrower still.
4. That further narrows the recommendations.

The autoplay behavior, with no opt-out and volume that overrides the user's choice, is the clearest technical sign that the product is designed to maximize browsing time. That matches how users interpret the algorithm's intent (UXR-10). We don't know whether the engine is actually tuned for browsing time or for watching titles to completion, but users experience it as tuned for browsing time.

- **Rewatches and abandoned sessions feed back into the engine and narrow recommendations further.** **High**
- **Autoplay behavior reinforces the impression that the product is designed to keep users scrolling.** **Medium**
- **Users don't trust the algorithm and prefer friends or human curators, a trend linked to at least one cancellation (UXR-04).** **High**

### Evidence Gaps

- **Recommendation performance:** no data on click-through, watching from a recommendation, how much of the catalog gets recommended, or recommendation variety.
- **BUG-1091:** no repro rate, volume, or breakdown by user group or genre.
- **Data flow:** no confirmation that watchlist, resume and completion data feed the recommendation engine.
- **Feedback controls:** the data doesn't say whether users can give explicit negative feedback such as "not interested."
- **Optimization target:** no documentation of what the engine is tuned for.

### Summary

The trust problem has one direct technical cause in the data: low-variety recommendations (BUG-1091). The other likely causes are inferred from adjacent bugs: thin title descriptions (from the search failures), unreliable viewing data (from the sync defects), and a self-reinforcing loop with the product's engagement-driven design. Together they explain the user stories well, but most of the causal links still need to be confirmed against the engine's actual design and data.
