# Task Manager

A simple task manager app with a Python/Flask backend and vanilla HTML/JS frontend.
This project has **intentional bugs** filed as GitHub issues, to be resolved by a
coding agent through the AgentCore GitHub MCP Gateway.

## Running Locally

### Backend

```bash
cd backend
pip install -r requirements.txt
python app.py
```

The API runs at `http://localhost:5000`.

### Frontend

```bash
cd frontend
python -m http.server 8080
```

Open `http://localhost:8080`.

## Known Bugs (filed as issues)

| # | Area | Bug |
|---|------|-----|
| 1 | Backend | `POST /tasks` — task ID is never incremented (all tasks get `id=1`) |
| 2 | Backend | `DELETE /tasks/:id` — filter logic is inverted (deletes everything except the target) |
| 3 | Backend | `PUT /tasks/:id` — `updated_at` timestamp is never refreshed |
| 4 | Backend | `PUT /tasks/:id` — no validation on `status` field (accepts any string) |
| 5 | Backend | `GET /tasks?status=` — case-sensitive comparison (won't match "Done" vs "done") |
| 6 | Backend | `GET /tasks/stats` — counter always sets to 1 instead of incrementing |
| 7 | Frontend | Status cycle skips "doing" — goes directly from "todo" to "done" |
| 8 | Frontend | `formatDate` crashes if `created_at` is null/undefined |
| 9 | Frontend | Error message never hides after being shown |
