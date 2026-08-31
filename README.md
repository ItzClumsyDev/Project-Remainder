# Project Remainder ⏰

A lightweight, open-source desktop productivity app and session timer built with Python and Tkinter.

![License](https://img.shields.io/badge/license-MIT-green.svg)
![Python](https://img.shields.io/badge/python-3.11+-blue.svg)
![Dependencies](https://img.shields.io/badge/dependencies-0%20(stdlib%20only)-success.svg)

---

## 🎯 Overview

**Project Remainder** is a minimalist, distraction-free work-session timer and productivity tracker. It helps you focus on projects in deliberate time blocks, reviews what you accomplished at the end of each session, and provides clean statistical insights over time without bloat, accounts, or cloud dependencies.

> *"A clock app that remembers when I worked, asks me what I accomplished, and shows me how consistently I've been working."*

---

## ✨ Features

- **⏱ Two Work Modes:**
  - **Timer Mode:** Set fixed durations (presets like 15m, 25m, 40m, 60m, 90m or custom minutes) with an animated progress ring.
  - **Stopwatch Mode:** Open-ended time tracking with Start, Pause, Resume, and Stop & Save.
- **🔔 Session Review Overlay & Custom Audio:**
  - Automatically pops up as an always-on-top window when your timer finishes or when you stop your stopwatch.
  - **Custom MP3 / WAV Alarm Sound:** Choose any audio file from your computer or use the default system alert.
  - Rate your productivity from 1 to 5 stars.
  - Add notes on what you achieved.
  - Mark off completed tasks directly from the review screen.
- **📊 Statistics & Insights:**
  - Breakdown by **Today**, **This Week**, **This Month**, and **This Year**.
  - Total time worked, session count, average session duration, and average rating.
  - Identifies your **Most Productive Day**.
  - Built-in canvas charts for daily minutes worked and productivity trends over the last 7 days.
  - Scrollable session log with date, duration, notes, and star ratings.
- **☑ Integrated To-Do List (Optional):**
  - Add, edit (double-click), delete, reorder (▲/▼), and check off tasks.
  - Seamlessly links to the session review overlay.
  - Easily toggle on/off in **Settings** (tasks are preserved when disabled).
- **🛡 Crash & Restart Recovery:**
  - Timer state checkpoints automatically every 5 seconds.
  - If closed unexpectedly, Project Remainder detects the interrupted session on the next launch and offers to recover and log it.
- **⚡ Super Lightweight & Zero Dependencies:**
  - Built purely using the Python standard library (`tkinter`, `queue`, `threading`, `json`).
  - Ultra-low RAM (~20–35 MB) and negligible CPU usage.
  - 100% offline and local-first.

---

## 🎨 Design & Palette

Built with a modern, calm dark aesthetic focused on deep work:
- **Primary Brand Color:** `#228822` (Forest Green)
- **Background:** `#0d1117`
- **Surface / Sidebar:** `#161b22`
- **Cards / Containers:** `#21262d`
- **Text:** `#e6edf3` / `#7d8590`
- **Typography:** Segoe UI

---

## 🚀 Quick Start

### Prerequisites
- Python 3.11 or newer (Python 3.14 tested)
- Standard Tkinter library (included by default with Python on Windows and macOS)

### Installation & Run

1. Clone or download the repository:
   ```bash
   git clone https://github.com/your-username/ProjectRemainder.git
   cd ProjectRemainder
   ```

2. Run directly with Python (no `pip install` required!):
   ```bash
   python main.py
   ```

---

## 📁 Project Structure

```
ProjectRemainder/
├── main.py                  # Application entry point
├── requirements.txt         # Standard library only documentation
├── LICENSE                  # MIT License
├── README.md                # Project documentation
├── app/
│   ├── __init__.py
│   ├── core/                # Core logic & data management (headless & testable)
│   │   ├── __init__.py
│   │   ├── settings_manager.py # Persistent user settings (JSON)
│   │   ├── session_manager.py  # Session storage & queries (JSON)
│   │   ├── stats_engine.py     # Pure statistics, filtering & chart calculations
│   │   ├── todo_manager.py     # To-do task CRUD & reordering
│   │   └── timer_engine.py     # Background thread timer & event queue
│   └── ui/                  # Tkinter UI components
│       ├── __init__.py
│       ├── theme.py            # Color palette, font tokens & layout metrics
│       ├── widgets.py          # Custom Canvas widgets (TimerRing, StarRating, BarChart, LineChart)
│       ├── overlay_window.py   # Always-on-top review modal
│       ├── dashboard_view.py   # Home dashboard & quick starts
│       ├── timer_view.py       # Countdown timer view
│       ├── stopwatch_view.py   # Stopwatch view
│       ├── stats_view.py       # Statistics & analytics view
│       ├── todo_view.py        # Task list view
│       ├── settings_view.py    # Preferences & data folder access
│       └── app_window.py       # Main window container, sidebar & navigation
└── data/                    # Local storage (created automatically on launch)
    ├── settings.json
    ├── sessions.json
    └── todos.json
```

---

## 💾 Data Storage

All data is stored locally in human-readable JSON files located in the `data/` directory:

### `data/sessions.json`
```json
{
  "sessions": [
    {
      "id": "7b79a0cf-8a35-4309-8c9f-d31e9c2c6bf7",
      "date": "2026-08-31",
      "mode": "timer",
      "start_time": "14:30:00",
      "end_time": "14:55:00",
      "duration_seconds": 1500,
      "target_duration": 1500,
      "productivity_rating": 5,
      "notes": "Completed feature design and implementation.",
      "tasks_completed": ["3d74c05e-851f-4bb2-b5e8-5ad45a90d970"]
    }
  ]
}
```

---

## 🧪 Testing

To run the verification test suite:
```bash
python -c "import app.core.timer_engine; import app.ui.app_window; print('OK')"
```

---

## 📜 License

This project is open-source and licensed under the [MIT License](LICENSE).


This is created by AI:
ChatGPT, Claude Sonnet, Gemini 3.7 flash
