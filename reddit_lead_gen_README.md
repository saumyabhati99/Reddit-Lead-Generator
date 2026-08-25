# Reddit Lead Generator

An automated n8n workflow that finds potential B2B leads on Reddit, scores them for buying intent using AI, and routes the best ones to a human for approval before anything is logged as a real lead.

## The Problem

Sales and growth teams often miss good leads because relevant conversations happen scattered across Reddit threads, and manually scanning subreddits for "someone looking for a tool" posts doesn't scale. This workflow automates that discovery process while keeping a human in control of what actually gets acted on.

## How It Works

1. **Monitors Reddit daily** — pulls new posts from r/SaaS, r/Entrepreneur, and a live search for phrases like "looking for a tool" or "recommend a CRM."
2. **Filters for buying signals** — keeps only posts containing intent phrases ("looking for," "switching from," "frustrated with," "which tool," etc.) and removes duplicates.
3. **Scores intent with AI (Gemini)** — each post is rated 1–10 for how close the author is to an actual purchase decision, with reasoning and a suggested reply drafted automatically.
4. **Checks the author's credibility** — looks up the poster's Reddit history to filter out low-quality or spam accounts before wasting a human's time on them.
5. **Sends a Telegram alert for high-intent leads** — includes the score, the pain point, the reasoning, and a drafted reply.
6. **Waits for human approval** — nothing gets logged as an approved lead until a person replies APPROVE or SKIP in Telegram. This keeps the system assistive, not autonomous.
7. **Logs everything to Google Sheets** — high-intent, low-intent, and approved leads are tracked separately for later follow-up and reporting.
8. **Sends a weekly strategy digest** — every Monday, Gemini reviews the week's data and sends a short GTM summary: intent trends, common pain points, and a recommended action for the BD team.

## Tools Used
n8n · Google Gemini (AI scoring & summarization) · Telegram (alerts & approval) · Google Sheets (lead tracking) · Reddit RSS feeds

## Why This Matters
This isn't just "AI finds leads" — it's a full pipeline with quality control at two points (author credibility check, human approval) before anything is treated as a real opportunity. It reflects how I approach automation generally: use AI to remove manual grunt work, but keep a human decision point wherever judgment actually matters.
