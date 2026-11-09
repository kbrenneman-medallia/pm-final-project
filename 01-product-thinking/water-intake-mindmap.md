# Mindmap: Daily Water Intake Tracker (Mobile App)

> **Module 1 · Product thinking exercise.** A product mindmap for a mobile app that helps people track how much water they drink each day. It covers three areas: **user needs** (why people would use it), **features** (what we could build), and **potential problems** (what could go wrong).

## Mindmap

```mermaid
mindmap
  root((💧 Water Intake<br/>Tracker App))
    User Needs
      Know how much to drink
        Personal daily goal
        Goal adjusts for weight, activity, climate
      Log with very little effort
        One tap, under 3 seconds
        No need to open the app
      Remember to drink
        Reminders at the right moments
        Reminders that don't nag
      See progress and stay motivated
        Visual progress today
        Streaks and trends over time
      Health context
        Pregnancy, breastfeeding
        Athletes and heavy sweaters
        Kidney stones, UTIs, doctor's orders
        Older adults with weaker thirst
      Trust and privacy
        Health data stays private
        Control over sharing
    Features
      Core MVP
        Quick-add buttons for common sizes
        Custom containers like my bottle
        Daily goal with progress ring
        Smart reminders
        History and undo
      Effortless logging
        Home and lock screen widgets
        Smartwatch app
        Voice logging
        Smart bottle sync over Bluetooth
      Personalization
        Onboarding goal calculator
        Weather and workout aware goals
        Quiet hours and schedule
        Count other drinks like tea, coffee, food
      Motivation
        Streaks and badges
        Weekly insights
        Gentle, non-guilt messaging
      Integrations
        Apple Health and Health Connect
        Fitness trackers
        Calendar aware reminders
      Social optional
        Friend or team challenges
        Workplace wellness programs
      Business model
        Free core tracking
        Premium insights and themes
        No ads in reminders
    Potential Problems
      Engagement
        Logging fatigue after week 2
        Reminder fatigue leads to mute or uninstall
        Novelty wears off
      Data accuracy
        People forget to log
        Guessed amounts are wrong
        Other drinks and food not counted
      Health and safety
        Overhydration risk from aggressive goals
        Not a medical device, needs disclaimers
        Conditions where fluids must be limited
        Could feed obsessive tracking habits
      Market
        Crowded category, many free apps
        Built into some smartwatches and bottles
        Hard to stand out and charge money
      Technical
        Notifications blocked by OS battery rules
        Time zones and late nights split the day
        Wearable and health sync conflicts
      Privacy and compliance
        Health data is sensitive
        GDPR and app store health rules
        Third party SDK data sharing
      Measuring success
        Logged water is not actual water
        Hard to prove a health outcome
```

## Key takeaways

1. **Effort is the main enemy.** The biggest risk is that people stop logging, not that features are missing. Widgets, watch logging, and one-tap quick-add matter more than advanced analytics.
2. **Reminders can help or hurt retention.** Smart, context-aware reminders keep people using the app. Too many push people to mute it or uninstall. Reminder quality needs its own success metric.
3. **Personalization makes us different, and health safety limits it.** Goals that adapt to weather and activity are a real advantage. They need safe caps and clear medical disclaimers.
4. **The market is crowded and many apps are free.** Basic tracking won't win on its own. Our angle has to be a better habit loop with less effort.

## Open questions for discovery

- Which group feels the strongest pain: busy office workers, athletes, or people with medical guidance to drink more?
- Why do people stop using water trackers they already have, and when?
- How many reminders a day is too many?
- Would people pay for anything beyond basic tracking? If so, what?

## Draft success metrics

| Area | Metric |
|---|---|
| Activation | % of new users who log at least 3 times on day 1 |
| Engagement | Logging days per week (target ≥ 5) |
| Retention | Day 30 retention |
| Reminder health | Reminder → log conversion rate; % of users who mute notifications |
| Outcome (self-reported) | % of users who say they hit their goal more often after 4 weeks |
