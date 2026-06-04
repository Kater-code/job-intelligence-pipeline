# Job Intelligence Pipeline

> Automated job monitoring system with LLM-powered relevance scoring.  
> Built as a business process automation case study using n8n, OpenAI API, and Telegram.

---

## Business problem

Actively job-seeking professionals spend 2–3 hours daily manually checking job boards,
copying listings into spreadsheets, and assessing relevance — only to find that 80% of
reviewed postings don't match their profile. There is no deduplication, no structured
data extraction, and no prioritization mechanism.

**Estimated waste:** 10–15 hours/week per active job seeker.

---

## Solution

An automated n8n pipeline that runs every morning, collects new job postings via API,
scores each posting for relevance using GPT-4o-mini, and delivers a structured digest
to Telegram (@kater_bestjobs_bot).

**Result:** 2–3 hours/day reduced to a 5-minute review of pre-ranked results.

---

## Process: AS-IS vs TO-BE

| Step | AS-IS (manual) | TO-BE (automated) |
|------|----------------|-------------------|
| Data collection | Manual browsing across 4+ job boards | n8n HTTP Request via Remotive API |
| Deduplication | None | ID-based check |
| Relevance filtering | Manual reading (~80% irrelevant) | LLM scoring 0–10 with profile match |
| Data extraction | Copy-paste | Structured JSON: score, summary, url |
| Output | Unstructured notes | Telegram digest with ranked results |
| Time required | 2–3 hours/day | 5 minutes/day |

---

## Architecture
