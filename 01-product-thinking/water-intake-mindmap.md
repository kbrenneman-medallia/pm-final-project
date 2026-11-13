# Mindmap: Daily Water Intake Tracker (Mobile App)

> **Module 1 · Product thinking exercise.** A product mindmap for a mobile app that helps people track how much water they drink each day. It covers three areas: **user needs** (why people would use it), **features** (what we could build), and **potential problems** (what could go wrong).

## Mindmap

The map is split into four diagrams so each one stays readable: an overview first, then one diagram for each branch.

### Overview

```mermaid
mindmap
  root((💧 Water<br/>Tracker))
    User Needs
      Know my goal
      Easy logging
      Reminders
      Motivation
      Health context
      Privacy
    Features
      Core MVP
      Fast logging
      Personalization
      Motivation
      Integrations
      Social
      Business model
    Potential Problems
      Engagement
      Accuracy
      Health & safety
      Market
      Technical
      Privacy
      Measuring success
```

### 1. User needs: why people would use it

```mermaid
flowchart LR
    N([User Needs]):::root
    N --> N1[Know my goal]:::cat
    N --> N2[Easy logging]:::cat
    N --> N3[Reminders]:::cat
    N --> N4[Motivation]:::cat
    N --> N5[Health context]:::cat
    N --> N6[Privacy]:::cat
    N1 --> N1a[Personal daily target]
    N1 --> N1b[Adjusts for weight,<br/>activity, weather]
    N2 --> N2a[One tap, under 3 sec]
    N2 --> N2b[Log without<br/>opening the app]
    N3 --> N3a[Right moment]
    N3 --> N3b[Never naggy]
    N4 --> N4a[Progress today]
    N4 --> N4b[Streaks & trends]
    N5 --> N5a[Pregnancy]
    N5 --> N5b[Athletes]
    N5 --> N5c[Doctor's orders]
    N5 --> N5d[Older adults]
    N6 --> N6a[Data stays private]
    N6 --> N6b[I control sharing]
    classDef default fill:#e3f2fd,stroke:#90caf9,color:#000
    classDef root fill:#1565c0,color:#fff,stroke:#0d47a1,font-weight:bold
    classDef cat fill:#bbdefb,stroke:#1565c0,color:#000
```

### 2. Features: what we could build

```mermaid
flowchart LR
    F([Features]):::root
    F --> F1[Core MVP]:::cat
    F --> F2[Fast logging]:::cat
    F --> F3[Personalization]:::cat
    F --> F4[Motivation]:::cat
    F --> F5[Integrations]:::cat
    F --> F6[Social]:::cat
    F --> F7[Business model]:::cat
    F1 --> F1a[Quick-add sizes]
    F1 --> F1b[Custom bottles]
    F1 --> F1c[Goal progress ring]
    F1 --> F1d[Smart reminders]
    F1 --> F1e[History & undo]
    F2 --> F2a[Widgets]
    F2 --> F2b[Smartwatch]
    F2 --> F2c[Voice]
    F2 --> F2d[Smart bottle sync]
    F3 --> F3a[Goal calculator]
    F3 --> F3b[Weather & workout aware]
    F3 --> F3c[Quiet hours]
    F3 --> F3d[Count tea, coffee, food]
    F4 --> F4a[Streaks & badges]
    F4 --> F4b[Weekly insights]
    F4 --> F4c[No-guilt messages]
    F5 --> F5a[Apple Health /<br/>Health Connect]
    F5 --> F5b[Fitness trackers]
    F5 --> F5c[Calendar]
    F6 --> F6a[Friend challenges]
    F6 --> F6b[Workplace wellness]
    F7 --> F7a[Free core tracking]
    F7 --> F7b[Premium insights]
    F7 --> F7c[No ads in reminders]
    classDef default fill:#e8f5e9,stroke:#a5d6a7,color:#000
    classDef root fill:#2e7d32,color:#fff,stroke:#1b5e20,font-weight:bold
    classDef cat fill:#c8e6c9,stroke:#2e7d32,color:#000
```

### 3. Potential problems: what could go wrong

```mermaid
flowchart LR
    P([Potential Problems]):::root
    P --> P1[Engagement]:::cat
    P --> P2[Accuracy]:::cat
    P --> P3[Health & safety]:::cat
    P --> P4[Market]:::cat
    P --> P5[Technical]:::cat
    P --> P6[Privacy]:::cat
    P --> P7[Measuring success]:::cat
    P1 --> P1a[Logging fatigue<br/>after week 2]
    P1 --> P1b[Reminders get muted]
    P1 --> P1c[Novelty wears off]
    P2 --> P2a[Forgotten logs]
    P2 --> P2b[Guessed amounts]
    P2 --> P2c[Other drinks missed]
    P3 --> P3a[Overhydration risk]
    P3 --> P3b[Not a medical device]
    P3 --> P3c[Fluid-restricted users]
    P3 --> P3d[Obsessive tracking]
    P4 --> P4a[Crowded, many free apps]
    P4 --> P4b[Built into watches]
    P4 --> P4c[Hard to charge money]
    P5 --> P5a[OS blocks notifications]
    P5 --> P5b[Time zones split days]
    P5 --> P5c[Sync conflicts]
    P6 --> P6a[Sensitive health data]
    P6 --> P6b[GDPR & app store rules]
    P6 --> P6c[Third-party SDKs]
    P7 --> P7a[Logged ≠ drunk]
    P7 --> P7b[Hard to prove<br/>health outcome]
    classDef default fill:#ffebee,stroke:#ef9a9a,color:#000
    classDef root fill:#c62828,color:#fff,stroke:#8e0000,font-weight:bold
    classDef cat fill:#ffcdd2,stroke:#c62828,color:#000
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
