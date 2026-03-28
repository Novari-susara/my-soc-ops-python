<div align="center">

# 🎯 Soc Ops

**Social Bingo for in-person mixers — built with GitHub Copilot**

[![Python](https://img.shields.io/badge/Python-3.13-3776AB?logo=python&logoColor=white)](https://python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.115-009688?logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![HTMX](https://img.shields.io/badge/HTMX-No%20JS%20Framework-3D72D7)](https://htmx.org)
[![uv](https://img.shields.io/badge/uv-package%20manager-DE5FE9)](https://docs.astral.sh/uv)
[![Ruff](https://img.shields.io/badge/linter-ruff-FCC21B)](https://docs.astral.sh/ruff)

*Find people who match the questions. Tap a square. Get 5 in a row. Win!*

[▶ Play Demo](https://copilot-dev-days.github.io/agent-lab-python/app/) &nbsp;·&nbsp;
[📚 Workshop Guide](#-workshop-lab-guide) &nbsp;·&nbsp;
[🚀 Quick Start](#-quick-start)

</div>

---

## What is Soc Ops?

Soc Ops is a **real-time Social Bingo** web app built for conference mixers, team icebreakers, and workshops. Each player gets a randomized 5×5 bingo board filled with people-finding prompts — *"Find someone who has visited 3+ countries"*, *"Find someone who debugs with console.log"* — and races to get five in a row.

This project also serves as a **hands-on GitHub Copilot lab** that walks you through building a full-stack Python web app from scratch using AI pair programming.

---

## ✨ Features

| | |
|---|---|
| 🎲 **Randomized boards** | Every game generates a fresh, unique 5×5 board |
| ✅ **One-tap marking** | Tap a square to mark it — instant feedback with no page reload |
| 🏆 **Bingo detection** | Rows, columns, and both diagonals are checked automatically |
| 🔄 **Reset anytime** | Start a new game without refreshing the page |
| 📱 **Mobile-first** | Designed for phones — perfect for a room full of people |
| ⚡ **Zero JS framework** | HTMX handles all interactivity; no React, no Vue, no build step |

---

## 🚀 Quick Start

**Prerequisites:** Python 3.13+ and [`uv`](https://docs.astral.sh/uv/getting-started/installation/)

```bash
# 1. Clone the repo
git clone https://github.com/Novari-susara/my-soc-ops-python.git
cd my-soc-ops-python

# 2. Install dependencies
uv sync

# 3. Start the dev server
uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

Open **http://localhost:8000** in your browser — and you're playing! 🎉

---

## 🧰 Tech Stack

| Layer | Technology | Why |
|-------|-----------|-----|
| **Web framework** | [FastAPI](https://fastapi.tiangolo.com) | Fast, type-safe Python APIs |
| **Templating** | [Jinja2](https://jinja.palletsprojects.com) | Server-rendered HTML fragments |
| **Interactivity** | [HTMX](https://htmx.org) | DOM swaps without a JS framework |
| **Package manager** | [uv](https://docs.astral.sh/uv) | Blazing-fast Python package manager |
| **Linter** | [Ruff](https://docs.astral.sh/ruff) | Zero-config, lightning-fast linting |
| **Tests** | [pytest](https://pytest.org) | Simple and powerful test runner |

---

## 🕹️ How to Play

1. **Open the app** on your phone at the shared URL
2. **Press Start** — you get a unique randomized board
3. **Mingle!** Find a person in the room who matches a square's description
4. **Tap the square** to mark it when you find a match
5. **Get 5 in a row** — horizontally, vertically, or diagonally — to win 🏆
6. **Dismiss the modal** and keep playing to find more bingos!

> 💡 The center square is always a **FREE SPACE** — already marked for you.

---

## 🏗️ Project Structure

```
app/
├── main.py           # FastAPI routes → HTML fragments
├── game_logic.py     # Pure functions: generate_board, toggle_square, check_bingo
├── game_service.py   # Mutable GameSession dataclass; in-memory store
├── models.py         # Frozen Pydantic models: BingoSquareData, BingoLine, GameState
├── data.py           # Bingo question prompts
├── static/css/       # Tailwind-like utility classes
└── templates/        # Jinja2 templates & HTMX partials
tests/                # pytest test suite (25 tests)
workshop/             # Step-by-step lab guide (offline)
```

---

## 🧪 Development

```bash
uv run pytest            # run all 25 tests
uv run ruff check .      # lint the codebase
```

| Check | Command | Expected |
|-------|---------|----------|
| Tests | `uv run pytest` | 25 passed |
| Lint  | `uv run ruff check .` | All checks passed |

---

## 📚 Workshop Lab Guide

This project is the centerpiece of a **GitHub Copilot Dev Days** hands-on lab. Follow the guide to build it step-by-step with AI assistance:

| Part | Title | What you'll learn |
|------|-------|-------------------|
| [**00**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=00-overview) | Overview & Checklist | Prerequisites and goals |
| [**01**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=01-setup) | Setup & Context Engineering | Workspace instructions, Copilot context |
| [**02**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=02-design) | Design-First Frontend | HTMX, Jinja2, mobile-first CSS |
| [**03**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=03-quiz-master) | Custom Quiz Master | Custom Copilot agents & skills |
| [**04**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=04-multi-agent) | Multi-Agent Development | Orchestrating multiple AI agents |

> 📝 Guides are also available offline in the [`workshop/`](workshop/) folder.

---

## 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines. Please review the [Code of Conduct](CODE_OF_CONDUCT.md) before contributing.

---

## 📄 License

[MIT](LICENSE) — built with ❤️ for the GitHub Copilot Dev Days workshop.
