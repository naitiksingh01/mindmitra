# MindMitra: AI Mental Wellness Companion (Prototype)

IBM SkillsBuild internship project, aligned to **UN SDG 3: Good Health and Well-being**.

**Problem statement:** Lack of mental health support among youth results in stress and anxiety. MindMitra is a chatbot for mental wellness check-ins and guidance.

## What it does

- **Chat companion** that listens and replies to common student concerns (exams, anxiety, loneliness, sleep, anger, career worries).
- **Daily mood check-in** (score 1 to 5) with a 7-day trend chart and a short insight.
- **Coping tools** based on common CBT techniques: guided breathing (4-4-6), 5-4-3-2-1 grounding, thought reframing and journaling.
- **Crisis safety net:** if a message mentions self-harm or suicide, the bot stops normal coaching, shows Tele-MANAS (14416 / 1800-891-4416) and 112, and opens a help panel. A "Need help now?" button is always on screen.
- **Hindi and English** support. Typing in Hindi gets a Hindi reply.
- **Privacy by design:** all data (moods, journal) stays in your own browser. Nothing is sent to a server.

## How to run

No install needed. Open `index.html` in any modern browser (double-click it). An internet connection is only used to load fonts.

## How it works

| Part | Where in `index.html` |
|---|---|
| Text in English and Hindi | `T` object |
| Crisis detection | `CRISIS` regular expression, checked before anything else |
| Intent rules (exam, anxious, sad ...) | `INTENTS` list |
| Mood log and trend chart | `logMood`, `renderChart` |
| Coping tools | `toolBreathe`, `toolGround`, `toolReframe`, `toolJournal` |
| Local storage | `store` helper |

The prototype uses rules, not a live AI model. To upgrade it, keep the crisis check as it is and send other messages to an LLM through a small backend, using a system prompt that limits replies to approved coping techniques.

## Limits (be honest in your presentation)

- It supports wellbeing and does not diagnose. It is not a replacement for a doctor or counsellor.
- Rule-based replies are limited. The crisis keywords list should be reviewed by a mental health professional before real use.
- Helpline numbers are for India. Check them before sharing publicly.

## Future work

LLM-powered replies with guardrails, WhatsApp bot, more Indian languages, psychologist-reviewed content, anonymous dashboard for colleges, pilot with students.
