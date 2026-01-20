
# uv: An Extremely Fast, All-in-One Package and Project Manager

**uv** is an extremely fast, all-in-one package and project manager written in Rust that is designed to be a drop-in replacement for a variety of existing tools like `pip`, `pip-tools`, `virtualenv`, and `pyenv`.

---

## Key Features and Benefits of uv

- **Speed**  
  It is often **10–100x faster** than `pip` for dependency installation and resolution, especially with a warm cache.

- **Unified Tooling**  
  uv consolidates multiple aspects of Python project management into a single command-line interface, reducing the need for several separate tools.

- **Virtual Environments**  
  It can create and manage virtual environments efficiently, automatically handling their creation when needed and supporting isolation for projects.

- **Dependency Management**  
  uv handles project dependencies using modern standards like `pyproject.toml` and generates a cross-platform `uv.lock` file to ensure reproducible environments across different machines.

- **Python Version Management**  
  uv can install and manage different Python versions, eliminating the need for a separate tool like `pyenv`.

- **Pip Compatibility**  
  It offers a pip-compatible interface, allowing for a smooth migration from existing workflows by using familiar commands like `uv pip install` and `uv pip compile`.

- **Standalone Binary**  
  uv is a standalone binary and does not require a Python installation to run, which simplifies its installation and upgrades.

## How to install uv (using pip)
- **Open terminal/powershell**
  ```bash
  # Install
  pip install uv
  # Test if working by getting the version
  uv --version
  ```
## Example Commands

```bash
# Initialize a new project
uv init myproject
cd myproject

# Add dependencies
uv add requests fastapi

# Install packages via pip-compat
uv pip install flask
uv pip compile

# Sync your environment from lock file
uv sync

# Run a Python script with inline deps
uv run hello.py

# Update uv itself
uv self update
```

## Manage Multiple Python
```bash
# Display a list of installed and available Python versions that the uv tool can manage and use
uv python list
# Automatically download and install specific version of Python
uv python install 3.13.5
# Uninstall specific version of Python installed
uv python uninstall 3.13.5
```

## Create a python project complete with (.git, .gitignore, .python-version, main.py, pyproject.toml and README.md)

```bash
# Initialize a new project
uv init myproject
cd myproject
# run the project, this also creates the .venv(virtuanl environment) 
uv run main.py
# to add dependencies, edit the pyproject.toml
dependencies = ["request", "rich"]
# or manually add to dependencies via command line
uv add requests rich



```

