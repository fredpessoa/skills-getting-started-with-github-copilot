# Repository Instructions

## Project Overview

- This repository contains a small FastAPI application for Mergington High School extracurricular activities.
- The API and in-memory activity data are defined in `src/app.py`.
- The browser UI is served from `src/static/`; its JavaScript calls the API endpoints.
- Activity and participant data are held in memory and reset whenever the server restarts.

## Development

- Install dependencies with `pip install -r requirements.txt`.
- Run the app from the repository root with `python -m uvicorn src.app:app --reload`.
- The root route redirects to the static UI. FastAPI documentation is available at `/docs` and `/redoc`.
- Keep changes focused and follow the existing lightweight Python and vanilla JavaScript patterns.

## Tests

- Keep backend tests in a top-level `tests/` directory.
- Use `pytest`; include it in `requirements.txt` when adding the test suite.
- Run tests from the repository root with `python -m pytest`.
- The app module exposes a FastAPI `app` suitable for API tests. Be mindful that its activity data is shared in-process and mutable.

## API Behavior

- `GET /activities` returns the current activity data.
- `POST /activities/{activity_name}/signup?email=...` signs up a participant.
- Preserve existing response formats unless the task explicitly changes the API contract.