# Copilot Workspace Instructions

**Soc Ops** — Social Bingo game for in-person mixers. **FastAPI + Jinja2 + HTMX**, no JS framework.

## Pre-commit Checklist

- [ ] `uv run ruff check .` — zero lint errors
- [ ] `uv run uvicorn app.main:app --port 8000` — server starts clean
- [ ] `uv run pytest` — all 25 tests pass

## Key Commands

```bash
uv sync                                                          # install deps
uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000 # dev server
uv run pytest && uv run ruff check .                             # test + lint
```

> Never use VS Code Simple Browser — HTMX needs a real browser at http://localhost:8000.

## Architecture

| File | Role |
|---|---|
| `app/main.py` | FastAPI routes — each returns an HTML fragment |
| `app/game_service.py` | Mutable `GameSession` `@dataclass`; in-memory store |
| `app/game_logic.py` | **Pure functions only**: `generate_board`, `toggle_square`, `check_bingo` |
| `app/models.py` | Frozen Pydantic models: `BingoSquareData`, `BingoLine`, `GameState` |
| `app/templates/components/` | HTMX partial templates swapped by POST routes |
| `app/static/css/app.css` | Tailwind-like utility classes — extend here, no inline styles |

## Conventions

- Python 3.13 via `uv`. Type hints + snake_case everywhere.
- Models are frozen — use `.model_copy(update={…})` to derive new state.
- POST routes return **HTML fragments**, never JSON.
- State flow: `START → (POST /start) → PLAYING → (bingo) → BINGO → (dismiss-modal) → PLAYING`. Any state `→ (POST /reset) → START`.
- CSS: see [css-utilities.instructions.md](.github/instructions/css-utilities.instructions.md). Design principles: [frontend-design.instructions.md](.github/instructions/frontend-design.instructions.md).
