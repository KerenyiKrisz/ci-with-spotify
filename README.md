# Spotify EDA with a Modern CI Setup

Exploratory analysis of a Spotify tracks dataset, built mostly as an excuse to set up a clean, production-style Python workflow around it: Polars for the data, a Marimo notebook for the analysis, and a full CI pipeline on top.

## What it does

The analysis side is a Marimo notebook that loads the Spotify dataset and digs into it interactively. Nothing exotic on the data itself, the point of the repo is everything around the notebook.

I used Polars instead of pandas here to get comfortable with it, and it's noticeably faster on this kind of work. Plotly handles the charts.

## The workflow part

This is really what the repo is about. Every push and pull request runs through GitHub Actions:

- pytest for tests
- Ruff and Black for linting and formatting
- mypy for type checking
- a dev container plus uv so the environment is reproducible
- a Dockerfile, with the image built and pushed through CI as well

The idea was to practise the full loop, write the analysis, but also wrap it in the same checks and automation you'd want on a real project rather than leaving it as a loose notebook.

## Stack

Python, Polars, Plotly, Marimo, pytest, Ruff, Black, mypy, GitHub Actions, Docker, uv

## Running it

```
uv sync
uv run marimo run notebooks/spotify_eda.py
```

Tests and checks:

```
uv run pytest
uv run ruff check .
uv run black --check .
uv run mypy . --ignore-missing-imports
```

---
