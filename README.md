# Python CLI Template

A production-ready template for building Python CLI applications with [Typer](https://typer.tiangolo.com/).

## Features

- ✅ **Turnkey initialization workflow** - One-click GitHub Actions workflow to configure your CLI with custom names
- ✅ **Complete documentation** - Ready-to-use README, CONTRIBUTING, and USAGE guides automatically customized for your project
- ✅ Modern Python project structure with [uv](https://github.com/astral-sh/uv)
- ✅ Example CLI commands with subcommands
- ✅ Comprehensive test suite with pytest
- ✅ Code quality tools (Ruff for linting and formatting)
- ✅ Pre-commit hooks for automatic quality checks
- ✅ GitHub Actions CI/CD workflow (lint, format, test, docs, pre-commit hooks)
- ✅ Branch protection configuration
- ✅ Auto-generated usage documentation with Typer CLI
- ✅ Makefile for common development tasks

## Getting Started

### 1. Create Your Repository from This Template

1. Click the **Use this template** button at the top of this repository
2. Choose **Create a new repository** then enter a repository name (e.g., `mail-fetcher`)

### 2. Initialize Your Project

Initialize your project using the GitHub Actions workflow:

1. Go to your new repository's **Actions** tab
2. Select the **Initialize Repository** workflow
3. Click the **Run workflow** button
4. Enter your project's inputs:
   - **Package name**: Python module name with underscores (e.g., `mail_fetcher`)
   - **CLI name**: Command-line executable name, use hyphens for multi-word (e.g., `ma-fe`)
5. Click **Run workflow** (the job should show up shortly, otherwise refresh the page)
6. Once the success summary appears, **your CLI is ready to go!** 🎉

### 3. Install Your CLI

**Prerequisites:** [uv](https://github.com/astral-sh/uv) - Python package manager

Clone your repository locally and install:

```bash
# Install the CLI to ~/.local/bin
make install

# Test it out (replace with your CLI name)
<your-cli> hello --name World
```

## How the Initialization Workflow Works

The workflow automatically:

- ✅ Validates your inputs (prevents running twice)
- ✅ Renames the package directory
- ✅ Updates all configuration files (`pyproject.toml`, `Makefile`)
- ✅ Updates all imports in Python files
- ✅ Customizes documentation (`README.md`, `CONTRIBUTING.md`)
- ✅ Runs linting, formatting, and tests to ensure everything works
- ✅ Commits and pushes the changes
- ✅ Displays a summary with next steps

**Naming conventions:** This template follows [PEP 8](https://peps.python.org/pep-0008/) (underscores for Python modules) and [PEP 508](https://peps.python.org/pep-0508/) (hyphens for distribution names). The workflow enforces these conventions to ensure compatibility.


## Next Steps

### Optional: Configure Branch Protection

Branch protection is recommended to enforce CI checks before merging. See [SETUP.md](.github/SETUP.md) for details.

```bash
# Requires GitHub CLI (gh)
make github
```

This command will:
- ✅ Require all CI checks to pass (lint, format, test, docs, pre-commit hooks)
- ✅ Block force pushes and branch deletion
- ✅ Enable automatic branch deletion after merge

_Note: If not configured, pre-commit hooks will still enforce quality checks locally._

### Build Your CLI

Now you're ready to customize your CLI! See [CONTRIBUTING.md](CONTRIBUTING.md) for the detailed developer workflow.

Development workflow:

1. **Add new commands** in `<your_package_name>/commands/`
2. **Register commands** in `<your_package_name>/main.py`
3. **Write tests** in `tests/`
4. **Validate your changes**: `make validate`
5. **Generate docs**: `make docs`
6. **Customize documentation** - Update `CONTRIBUTING.md` and `README.md` with your project-specific details
