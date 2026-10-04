# FastAPI Blog

A small FastAPI blog app that renders posts with Jinja templates, Tailwind CSS, and local static assets.

## Features

- FastAPI app with template rendering
- Tailwind CSS based layout
- Static CSS, icons, favicon, and profile image assets
- JSON API endpoint for posts
- Hidden HTML routes from the OpenAPI schema

## Project Structure

```text
.
├── main.py
├── requirements.txt
├── static/
│   ├── css/
│   ├── icons/
│   ├── profile_pics/
│   └── site.webmanifest
└── templates/
    ├── home.html
    └── layout.html
```

## Setup

Create and activate a virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install dependencies:

```bash
python -m pip install -r requirements.txt
```

## Run Locally

```bash
fastapi dev main.py
```

Then open:

```text
http://127.0.0.1:8000
```

If port `8000` is already in use:

```bash
fastapi dev main.py --port 8001
```

## Routes

| Route | Description |
| --- | --- |
| `/` | Blog home page |
| `/posts` | Blog posts page |
| `/api/posts` | JSON API for posts |

## Notes

Static files are mounted in `main.py`:

```python
app.mount("/static", StaticFiles(directory="static"), name="static")
```

Templates use `url_for()` so static file URLs and named routes can be generated automatically.
