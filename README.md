# HireLens — AI-Powered Interview Simulator

An AI-driven mock interview platform that simulates real technical interviews across 9 computer science domains, evaluates spoken answers with speech-to-text and NLP, and generates detailed PDF performance reports.

## Features

- Voice-based interviews with real-time speech-to-text (OpenAI Whisper)
- Answer scoring that combines TF-IDF semantic similarity with speech analysis — pace, pauses, and fluency via librosa
- 150+ curated questions across 9 domains: DSA, DBMS, OS, Computer Networks, ML, OOP, Web Development, System Design, HR
- Automated PDF performance reports (ReportLab) with score breakdowns
- Session history persisted in SQLite
- Web UI built with Flask

## Tech Stack

Python · Flask · OpenAI Whisper · librosa · scikit-learn (TF-IDF) · ReportLab · SQLite · HTML/CSS/JS

## Project Structure

```
AI_Interview_Assessment/
├── backend/
│   ├── app.py                # Flask application entry point
│   ├── audio_processing.py   # Audio feature extraction (librosa)
│   ├── text_analysis.py      # Transcript processing & TF-IDF scoring
│   ├── scoring.py            # Content / confidence / fluency scoring
│   ├── explainability.py     # Human-readable score explanations
│   ├── adaptive_engine.py    # Adaptive question selection
│   └── question_bank.py      # 150+ curated questions across 9 domains
├── frontend/
│   ├── templates/            # HTML templates
│   └── static/               # CSS, JS, assets
└── data/
    ├── audio_samples/        # Recorded interview audio
    ├── reports/              # Generated PDF reports
    └── session_history.json  # Session metadata
```

## Getting Started

### Prerequisites

- Python 3.10+
- `ffmpeg` (required by Whisper/librosa for audio decoding)

### Setup

```bash
# Clone the repo
git clone https://github.com/OjasviTanwar/AI_Interview_Assessment.git
cd AI_Interview_Assessment

# Create and activate a virtual environment
python -m venv venv
# Windows:
venv\Scripts\activate
# macOS / Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run the app
python backend/app.py
```

Then open http://127.0.0.1:5000 in your browser.

> Note: the first run downloads the Whisper speech model (~140 MB), so allow a few extra minutes.

## How It Works

1. Pick an interview domain (DSA, DBMS, OS, …).
2. Answer questions by voice — your audio is transcribed with Whisper.
3. librosa extracts speech features (words per minute, pause count, …).
4. TF-IDF scoring compares your answer semantically against reference answers.
5. You get a scored report, downloadable as a PDF.

## Research

This project was documented as an IEEE-format research paper and presented to an academic panel.

## Author

Ojasvi Tanwar — B.Tech Computer Science & Engineering (2026)
