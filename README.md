# 📖 Manuscript Editor — AI Agent
### Built for Romance & Drama novel editing | Portfolio project

---

## What this app does

This is an AI-powered manuscript editor built with Python and multiple AI providers (Claude, ChatGPT, Gemini).
You upload or paste a chapter from your novel, and the AI gives you detailed editorial
feedback across four dimensions:

- **Grammar & Style** — prose clarity, sentence rhythm, word choice
- **Plot Consistency** — logical coherence, timeline, continuity
- **Character Voice** — distinct personalities, authentic dialogue
- **Pacing & Structure** — romantic tension, dramatic beats, momentum

You can track progress across all 73 chapters, export feedback as Word or PDF,
and compare original text side-by-side with editorial notes.

---

## How to run this app (step by step, no coding needed)

### Step 1 — Install Python
1. Go to https://www.python.org/downloads/
2. Click the big yellow "Download Python" button
3. Run the installer — on Windows, tick **"Add Python to PATH"** before clicking Install

### Step 2 — Get your Anthropic API key
1. Go to https://console.anthropic.com
2. Sign up or log in
3. Click **"API Keys"** in the left menu → **"Create Key"**
4. Copy the key (starts with `sk-ant-...`) — save it somewhere safe

### Step 3 — Download this app
1. Save the files (`app.py` and `requirements.txt`) into a folder on your computer
   e.g. a folder called `manuscript-editor` on your Desktop

### Step 4 — Open Terminal / Command Prompt
- **Mac**: Press Cmd+Space, type "Terminal", press Enter
- **Windows**: Press the Windows key, type "cmd", press Enter

### Step 5 — Navigate to your folder
Type this and press Enter (replace with your actual folder path):
```
cd Desktop/manuscript-editor
```

### Step 6 — Create a virtual environment (recommended)
```
python3 -m venv venv
```
This creates an isolated environment for the app's dependencies.

### Step 7 — Activate the virtual environment
- **Mac/Linux**: `source venv/bin/activate`
- **Windows**: `venv\Scripts\activate`

### Step 8 — Install dependencies (one time only)
```
pip install -r requirements.txt
```
Wait for it to finish (takes 1-2 minutes).

### Step 9 — Run the app
```
streamlit run app.py
```
Your browser will automatically open at `http://localhost:8501`

**Note**: Always activate the virtual environment (`source venv/bin/activate`) before running the app to ensure you're using the correct dependencies.

### Step 10 — Use the app
1. Paste your API key in the **sidebar** (left panel)
2. Add your character names and novel details
3. Go to the **Editor** tab
4. Paste a chapter or upload a `.txt` / `.docx` file
5. Click **Analyse manuscript →**
6. Download feedback as Word or PDF

---

## How to share this app online (for your PM portfolio)

### Option A — Streamlit Community Cloud (FREE, easiest)
1. Create a free account at https://github.com and upload your files
2. Go to https://share.streamlit.io
3. Sign in with GitHub → click "New app" → select your repo → set `app.py` as the main file
4. Click **Deploy** — you get a public URL like `yourname.streamlit.app`
5. Add the link to your LinkedIn / CV / portfolio

### Option B — Put the API key in Streamlit Secrets (so users don't need one)
In Streamlit Cloud, go to App Settings → Secrets and add:
```
ANTHROPIC_API_KEY = "sk-ant-your-key-here"
```
Then in app.py, the app will automatically pick it up.

---

## For your PM portfolio — talking points

- **Problem solved**: Manual manuscript editing is slow and expensive; this automates
  detailed editorial feedback in seconds
- **Tech stack**: Python, Streamlit, Anthropic Claude API, OpenAI ChatGPT API, Google Gemini API, ReportLab, python-docx
- **Key features**: Multi-mode AI analysis, chapter progress tracker, PDF/Word export,
  side-by-side compare view
- **Scale**: Designed for 73-chapter, 700+ page novels with per-chapter session tracking
- **User-centred design**: Built around a real use case (the author's own novel)

---

## Troubleshooting

**"streamlit: command not found"**
→ Try: `python -m streamlit run app.py`

**"ModuleNotFoundError"**
→ Ensure you're in the virtual environment: `source venv/bin/activate` (Mac/Linux) or `venv\Scripts\activate` (Windows), then run `pip install -r requirements.txt` again

**"AuthenticationError"**
→ Your API key is wrong — double-check it in the sidebar

**App runs but AI gives weird output**
→ Try a shorter excerpt (under 2,000 words works best)
