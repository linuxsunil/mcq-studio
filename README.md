# MCQ Studio — Rise 360 Question Builder

A free, open-source tool for Instructional Designers to build, review, and export multiple-choice questions (MCQs) for **Articulate Rise 360**.

🌐 **Live app:** [mcqstudio-1081064604778.asia-south1.run.app](https://mcqstudio-1081064604778.asia-south1.run.app)

---

## ✨ Features

- **AI-powered generation** — generate questions by topic using Claude, Gemini, GPT-4, or Azure OpenAI
- **Choice-specific feedback** — every answer option (A, B, C, D) gets its own tailored feedback message
- **Flexible attempt logic** — 1, 2, or 3 attempts with smart feedback reveal behaviour
- **3-pool system** — Easy / Medium / Hard pools with QA review before export
- **Configurable question ratio** — set exactly how many Easy, Medium, and Hard questions appear in your quiz (e.g. 3:2:1, 4:2:2, or any combination you need)
- **Question order control** — choose Shuffled (randomised per learner) or Fixed Order (Easy → Medium → Hard)
- **Display options** — show or hide the pool badge, progress bar, score screen, and restart button
- **Rise 360 ready** — exports self-contained HTML to paste into a Rise Code Block
- **QA preview** — preview individual questions or the full quiz in a new tab before exporting
- **Shareable test link** — share a standalone HTML file with IDs or Storyline devs to test before publishing
- **Upload via template** — bulk import questions from a .txt file using the MCQ Studio template format

---

## 🔒 Privacy

**Your API key never touches this server.**

Keys are stored only in your browser session and are sent directly from your browser to the AI provider (Anthropic, Google, OpenAI). They are cleared the moment you close the tab.

---

## 🚀 Getting Started

### Use the hosted version
Just open the live app URL above — no install needed.

### Run locally
```bash
git clone https://github.com/linuxsunil/mcq-studio.git
cd mcq-studio
pip install -r requirements.txt
python main.py
# Open http://localhost:8080
```

---

## 🔑 Getting an API Key

| Provider | Dashboard |
|----------|-----------|
| Anthropic (Claude) | console.anthropic.com |
| Google (Gemini) | aistudio.google.com |
| OpenAI (GPT-4) | platform.openai.com |

---

## 📄 Question Template Format

Upload questions in bulk using a .txt file with this structure:

```
[QUESTION]
[POOL]: easy | medium | hard
[Q]: Question text here
[A]: Option A text
[B]: Option B text
[C]: Option C text
[D]: Option D text
[CORRECT]: B
[FB_A]: Feedback explaining why A is wrong
[FB_B]: Feedback explaining why B is correct
[FB_C]: Feedback explaining why C is wrong
[FB_D]: Feedback explaining why D is wrong
```

Sample question banks are included in the repo.

---

## 🏗️ Deploy to Google Cloud Run

```bash
gcloud run deploy mcq-studio \
  --source . \
  --platform managed \
  --region asia-south1 \
  --allow-unauthenticated
```

---

## 📁 Repo Structure

```
mcq-studio/
├── index.html              # The full app (single file)
├── main.py                 # Flask server for Cloud Run
├── requirements.txt        # Python dependencies
├── .gitignore
├── README.md
└── DS_ML_30Q_ChoiceSpecific.docx   # Sample question bank
```

---

## 📝 Feedback Behaviour

| Scenario | What the learner sees |
|----------|-----------------------|
| Correct answer (any attempt) | That option's specific feedback immediately |
| Wrong answer, not final attempt | Generic "Not quite, try again" |
| Wrong answer, final attempt | That option's specific feedback + correct answer revealed |

---

## ⚙️ Configuration Options

| Setting | Options |
|---------|---------|
| Brand colours | Primary, correct, incorrect, background |
| Quiz title | Any text |
| Attempts | 1, 2, or 3 |
| Question ratio | Any number per pool (e.g. 2 Easy, 3 Medium, 2 Hard) |
| Question order | Shuffled or Fixed (Easy → Medium → Hard) |
| Pool badge | Show / Hide |
| Progress bar | Show / Hide |
| Score screen | Show / Hide |
| Restart button | Show / Hide |

---

## License

MIT — free to use, share, and modify.
