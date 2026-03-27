# 📖 Manuscript Editor — AI Agent

> An AI-powered editorial agent for fiction writers preparing novels for publication. Built as a real-world tool for editing a 73-chapter, 700+ page Romance/Drama novel across 16 planned titles.

![Python](https://img.shields.io/badge/Python-3.14-blue) ![Streamlit](https://img.shields.io/badge/Streamlit-1.35-red) ![AI](https://img.shields.io/badge/AI-Claude%20%7C%20ChatGPT%20%7C%20Gemini-green) ![Status](https://img.shields.io/badge/Status-v1%20Working-brightgreen)

---

## The Problem

Professional manuscript editing costs $0.01–0.05 per word — for a 200,000 word novel that's $2,000–$10,000 per title. For an author with 16 novels to publish, this is prohibitive. Existing AI tools treat every chapter in isolation, missing cross-chapter continuity issues that a real editor would catch.

## The Solution

An AI editorial agent that reads your manuscript and returns structured, actionable feedback — not generic writing advice, but specific notes tied to your actual text, your characters, and your story.

---

## Features (v1)

- **Multi-provider AI** — switch between Claude, ChatGPT, and Gemini from the sidebar
- **Full manuscript upload** — upload `.txt` or `.docx` files, or paste text directly
- **4-dimension editorial feedback** — Line Edits & Prose, Scene Structure, Character & Dialogue, Emotional Impact
- **Scores + suggested rewrites** — every section includes a score out of 10 and a concrete rewrite example from your actual text
- **Chapter history tracker** — tracks all chapters analysed with average scores across the novel
- **Export as Word or PDF** — download editorial notes in a format you can work from
- **Side-by-side compare** — original manuscript next to editorial notes
- **API key persistence** — keys stored in `.env` file, never re-enter them

---

## Roadmap (v2)

See [Issues](https://github.com/nilanjana281/manuscript-editor/issues) for the full backlog. Key features planned:

- [ ] **Novel map** — auto-extract characters, timeline, plot arcs on first upload
- [ ] **Full manuscript chunking** — auto-split by chapter, process sequentially
- [ ] **Cross-chapter continuity checks** — catch character inconsistencies, plot holes, timeline errors across the whole novel
- [ ] **Structured JSON output** — chapter, line number, issue type, original text, suggestion (token-efficient)
- [ ] **Highlighted manuscript view** — render flagged passages like Copilot track changes
- [ ] **Persistent memory** — agent remembers previous editing sessions and builds on them
- [ ] **Chat mode** — ask questions about your specific novel ("what's wrong with the antagonist's arc in act 2?")
- [ ] **Multi-novel management** — manage 16 titles in one place

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend & app framework | Streamlit |
| Language | Python 3.14 |
| AI providers | Anthropic Claude, OpenAI GPT-4o, Google Gemini |
| Document export | python-docx, ReportLab |
| Environment management | python-dotenv |
| Version control | Git / GitHub |

---

## Getting Started

### Prerequisites
- Python 3.8+
- An API key from one of: [Anthropic](https://console.anthropic.com), [OpenAI](https://platform.openai.com/api-keys), or [Google AI Studio](https://aistudio.google.com)

### Installation

```bash
git clone https://github.com/nilanjana281/manuscript-editor.git
cd manuscript-editor
pip3 install -r requirements.txt
streamlit run app.py
```

### API Key Setup

Create a `.env` file:

```
ANTHROPIC_API_KEY=sk-ant-...
OPENAI_API_KEY=sk-...
GEMINI_API_KEY=AIza...
```

Only fill in the one you want to use. Gemini has a free tier.

---

## How It Works

```
Your manuscript
      ↓
Streamlit UI (upload / paste)
      ↓
Python builds editorial prompt
      ↓
AI provider (Claude / ChatGPT / Gemini)
      ↓
Structured JSON response
      ↓
Rendered feedback with scores + rewrites
      ↓
Export as Word / PDF
```

---

## Project Context

This is a real tool built for a real problem — not a hackathon demo. The author has a completed novel (73 chapters, 203,000 words) ready for editing and 15 more planned for publication.

Built by [Nilanjana Chatterjee](https://nilanjana281.github.io/github.io/) — Senior Product Manager specialising in AI-powered products.

---

## Contributing

Issues and PRs welcome. See [Issues](https://github.com/nilanjana281/manuscript-editor/issues) for the current backlog.

---

## Troubleshooting

**`streamlit: command not found`** → Use `python3 -m streamlit run app.py`

**`ModuleNotFoundError`** → Run `pip3 install -r requirements.txt`

**`429 quota exceeded` on Gemini** → Link billing account at console.cloud.google.com (free tier still applies)

**`Invalid API key`** → Check `.env` — no spaces around `=`, no quotes around the key
