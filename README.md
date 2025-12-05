# Spotify EDA with Modern CI/CD

> 📊 Exploratory Data Analysis on Spotify tracks using **Polars** + **Marimo**, with a complete **GitHub Actions CI/CD pipeline** demonstrating production-ready Python development practices.

---

## 🎯 Overview

This project showcases:
- **Interactive Data Analysis** – Marimo notebook for live Spotify data exploration
- **Modern Python Stack** – Polars for efficient data processing, Plotly for visualization
- **Production CI/CD** – Automated testing, linting, formatting, and type checking with GitHub Actions
- **Dev Environment** – Dev Container + `uv` for reproducible, isolated development
- **Best Practices** – Code quality tools (Ruff, Black, mypy) integrated into the workflow

### Key Features

✅ **Automated Testing** – pytest with CI integration  
✅ **Linting & Formatting** – Ruff + Black for clean, consistent code  
✅ **Type Safety** – mypy for static type checking  
✅ **Reproducible Environment** – Dev Container + uv lock file  
✅ **Easy to Run** – Single command to start the interactive notebook  

---

## 🚀 Quick Start

### Prerequisites
- Python 3.12+
- `uv` package manager ([install](https://docs.astral.sh/uv/getting-started/installation/))

### Installation & Setup

```bash
# Clone the repository
git clone https://github.com/KerenyiKrisz/ci-with-spotify.git
cd ci-with-spotify

# Install dependencies
uv sync

# Run the interactive notebook
uv run marimo run notebooks/spotify_eda.py
```

### Run Tests & Code Quality Checks

```bash
# Run all tests
uv run pytest

# Lint with Ruff
uv run ruff check .

# Check formatting with Black
uv run black --check .

# Type check with mypy
uv run mypy . --ignore-missing-imports
```

---

## 📁 Project Structure

```
ci-with-spotify/
├── .github/workflows/        # GitHub Actions CI/CD pipeline
│   └── python_app.yaml       # Automated testing, linting, type checking
├── .devcontainer/            # Dev Container configuration
├── notebooks/
│   └── spotify_eda.py        # Marimo notebook for interactive EDA
├── tests/
│   └── test_utility.py       # Unit tests
├── main.py                   # Entry point
├── pyproject.toml            # Project metadata & dependencies
└── README.md                 # This file
```

---

## 🔄 GitHub Actions Workflow

The CI pipeline automatically runs on every push and pull request to `main`:

| Step | Tool | Purpose |
|------|------|---------|
| **Install Dependencies** | uv | Sync Python environment |
| **Run Tests** | pytest | Execute unit tests |
| **Lint Code** | Ruff | Check for code issues |
| **Format Check** | Black | Verify code formatting |
| **Type Check** | mypy | Static type validation |

All checks must pass before merging to `main`. This ensures code quality and consistency.

---

## 🛠️ Technologies

| Category | Tools |
|----------|-------|
| **Data Processing** | Polars, NumPy, Pandas |
| **Visualization** | Plotly Express |
| **Interactive Notebook** | Marimo |
| **Package Management** | uv, pip |
| **Testing** | pytest |
| **Code Quality** | Ruff, Black, mypy |
| **CI/CD** | GitHub Actions |
| **Dev Environment** | Dev Container, Docker |

---

## 📊 Spotify EDA Notebook

The main interactive analysis is in `notebooks/spotify_eda.py`, a Marimo notebook that:
- Loads Spotify tracks dataset
- Performs exploratory data analysis
- Creates interactive visualizations
- Demonstrates Polars best practices

**Run the notebook:**
```bash
uv run marimo run notebooks/spotify_eda.py
```

---

## 🧪 Testing

Unit tests are located in `tests/test_utility.py`. Run with:

```bash
uv run pytest
```

Or with coverage:
```bash
uv run pytest --cov
```

---

## 📋 Development Practices

### Code Quality Standards
- **Linting:** Ruff checks for errors, complexity, and style violations
- **Formatting:** Black enforces consistent code style (127-char line length)
- **Type Safety:** mypy ensures type correctness
- **Testing:** All changes must pass pytest

### Contributing

To contribute:
1. Create a feature branch
2. Make changes and run local checks:
   ```bash
   uv run ruff check .
   uv run black .
   uv run mypy . --ignore-missing-imports
   uv run pytest
   ```
3. Push and create a pull request – CI will validate automatically

---

## 🐳 Dev Container

This repo includes `.devcontainer/devcontainer.json` for a reproducible development environment using Docker:

- **Includes:** Python 3.12, uv, VS Code extensions
- **Pre-configured:** Environment synced automatically on startup
- **VS Code Integration:** Works with local or GitHub Codespaces

Use with:
```bash
# GitHub Codespaces (web-based)
# Create from "Code" → "Codespaces" button

# Local VS Code with Docker
# Install Dev Containers extension, then reopen folder in container
```

---

## 📈 Why This Project?

This repository demonstrates **production-ready Python development** by combining:

1. **Practical Data Analysis** – Real Spotify data with Polars/Marimo
2. **Best Practices** – Type hints, testing, linting, formatting
3. **DevOps Fundamentals** – CI/CD pipelines, containerization, automation
4. **Team Collaboration** – Code quality gates ensure consistency

It's a portfolio piece showing I understand the full software development lifecycle—from writing clean code to automating quality checks.

---

## 📝 License

This project is licensed under the MIT License – see the LICENSE file for details.

---

## 🤝 Contact

- **GitHub:** [KerenyiKrisz](https://github.com/KerenyiKrisz)
- **Project:** [ci-with-spotify](https://github.com/KerenyiKrisz/ci-with-spotify)

---

*Built with ❤️ using Python, Polars, and GitHub Actions.*

On a repository without any GitHub Actions configured, some templates are
provided to help you get started. We've used the `Python application` template,
which sets up a workflow to:
* Check out the repository code
* Set up Python
* Install dependencies
* Run tests and checks

Unfortunately, the workflow is incomplete and doesn't use very modern tooling. For
example it uses `pip` to install dependencies, rather than `uv`.

To use `uv` in the workflow, we know we first need to install it. For most common
CI tasks, a GitHub Action worklow already exists. Installing `uv` is one of these
common tasks, so we might think about searching the
[GitHub Actions Marketplace](https://github.com/marketplace?type=actions) for a
suitable "uv" workflow. Look for the official one and use the examples within.

### Exercise

Next, have a look at the rest of the workflow file and complete the TODOs that are
listed within it.

**I'd recommend snoozing GitHub Copilot and having a go yourself first!**

### Triggering GitHub Actions

First, commit and push any changes to the workflow configuration to GitHub. This
should trigger the workflow run, which you can monitor from the repository page
on GitHub, under the `Actions` tab.

Are there any issues? If so, you would come back to the Codespace to fix them and
push again until the workflow runs successfully.

Let's now make some changes to the notebook itself.

### Exercises

* Add type hints to the utility function in the Notebook.
    - You can add type hints to arguments, and to the return type.
* Add a test for the utility function in `tests/test_utility.py`.
    - You may overwrite the existing placeholder test function.

**Feel encouraged to use GitHub Copilot to guide the way.**

## Docker Configuration

Docker is a platform for developing, sharing, and running applications. It
uses containerisation technology to package an application and its dependencies.

It aims to solve the problem of "it works on my machine" by providing a consistent
environment from development to production. Many cloud platforms support Docker
containers natively, so they are a great way to package applications for deployment.

This repo contains a Dockerfile in the project root that builds a Docker image
for the app. Have a look! We choose a base image, install `uv`, copy over all the
important project files, `sync` the environment, expose a port and define a command to run
the app.

### Triggering a Docker Build

We can use continuous integration to build and push Docker images too. 
First we have to enable the appropriate permissions on our repository, via
Settings:

![Changing GH Action permissions](assets/action-permissions.png)

Now let's add a new GitHub Action to do this. Building Docker images is another
common task, so we might go back to the
[GitHub Actions Marketplace](https://github.com/marketplace?type=actions) for a
suitable "Docker" workflow.

We can see the *Build and push Docker images* action and the examples within
to create a new workflow for ourselves. You can copy the `container.yaml` file
from the `complete/` directory in this Codespace, or create your own from scratch.

Once copied in, commit and push the changes to GitHub to trigger the workflow.
We'll look at using this Docker image in the next session.

Note that we added these permissions:

```yaml
permissions:
  contents: read
  packages: write
```


# The End!