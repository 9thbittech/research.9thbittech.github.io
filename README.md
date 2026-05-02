# 9th Bit Labs — Research

> Deep-dive articles on AI engineering, LLM agents, RAG, automation ROI, and applied machine learning — grounded in real production deployments.

**Live site:** [research.9thbittech.github.io](https://research.9thbittech.github.io)  
**Parent site:** [9thbit.org](https://9thbit.org)

---

## Overview

This is the research publication subsite for [9th Bit Labs](https://9thbit.org). It hosts practitioner-written technical articles covering:

- **LLM Agents & Autonomous Pipelines** — orchestration patterns, tool-use, failure modes
- **RAG in Production** — chunking strategies, hybrid search, re-ranking, evaluation metrics
- **AI Automation ROI** — measurement frameworks, instrumentation, 90-day assessment cycles
- **Fine-Tuning vs RAG** — decision heuristics and combined architecture patterns

---

## Project Structure

```
research.9thbittech.github.io/
│
├── index.html          # Article listing page (fetches from articles.json)
├── article.html        # Article detail page (shows abstract + action buttons)
├── articles.json       # Article data source — all content lives here
├── papers/             # PDF papers directory (place PDFs here)
└── README.md
```

---

## How It Works

All article data is stored in `articles.json`. Both `index.html` and `article.html` fetch this file at runtime — no build step required.

### Adding a New Article

Edit `articles.json` and add a new entry to the `articles` array:

```json
{
  "id": "your-article-slug",
  "title": "Your Article Title",
  "slug": "your-article-slug",
  "date": "2026-05-01",
  "readTime": "8 min read",
  "category": "AI Research",
  "tags": ["Tag1", "Tag2"],
  "author": {
    "name": "9th Bit Labs Research",
    "role": "AI Engineering Team"
  },
  "excerpt": "A 1–2 sentence summary shown on the card.",
  "abstract": "A 3–5 sentence academic abstract shown on the article page.",
  "image": "https://images.unsplash.com/photo-XXXXX?w=800&q=80",
  "paperUrl": "papers/your-article-slug.pdf",
  "downloadUrl": "papers/your-article-slug.pdf",
  "featured": false,
  "sections": []
}
```

Then place the corresponding PDF in the `papers/` directory.

### Fields Reference

| Field | Required | Description |
|-------|----------|-------------|
| `id` / `slug` | ✅ | Unique identifier used in the URL (`article.html?id=slug`) |
| `title` | ✅ | Full article title |
| `date` | ✅ | Publication date (ISO format `YYYY-MM-DD`) |
| `readTime` | ✅ | Estimated read time shown on card |
| `category` | ✅ | One of: `AI Research`, `Engineering`, `Strategy` |
| `tags` | ✅ | Array of topic tags |
| `excerpt` | ✅ | Short summary for the card (1–2 sentences) |
| `abstract` | ✅ | Full abstract shown on the article detail page |
| `image` | ✅ | Hero image URL (Unsplash or hosted image) |
| `paperUrl` | ✅ | Path to the PDF for "View Full Paper" button |
| `downloadUrl` | ✅ | Path to the PDF for "Download Paper" button |
| `featured` | ❌ | Set `true` on one article to mark it featured (optional) |
| `sections` | ❌ | Legacy field — leave as empty array `[]` |

---

## Deployment

This site is deployed via **GitHub Pages** from the `main` branch root.

GitHub Pages will automatically serve `index.html` at the repository's GitHub Pages URL.

### Steps to deploy changes

```bash
git add .
git commit -m "your commit message"
git push origin main
```

---

## Design System

| Token | Value | Usage |
|-------|-------|-------|
| `--ink` | `#0E0E0E` | Primary text, dark backgrounds |
| `--paper` | `#F5F2EC` | Page background, light text |
| `--paper-alt` | `#EAE6D9` | Card hover, abstract backgrounds |
| `--rust` | `#C94B20` | Accent color, buttons, borders |
| `--slate` | `#3A3A48` | Secondary text |
| `--muted` | `#7A7A82` | Meta text, labels |

**Fonts:** DM Serif Display (headings) · DM Sans (body) · Bebas Neue (stat numbers)

---

## Tech Stack

- Pure **HTML + CSS + Vanilla JavaScript** — zero dependencies, zero build step
- Data fetched client-side from `articles.json`
- Deployed on **GitHub Pages**

---

## License

© 2026 9th Bit Labs, Nagpur, India. All rights reserved.
