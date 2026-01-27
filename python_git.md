# Push local Python project to GitHub
Moving a local **uv** project to GitHub is a straightforward process. Since `uv` handles your virtual environment and dependencies efficiently, you just need to make sure you're pushing the right files and ignoring the ones that don't belong in version control.

Here is the step-by-step guide to doing this via the command line.

### 1. Initialize Git locally

First, navigate to your project root folder and turn it into a Git repository.

Bash

```
git init
```

### 2. Create a `.gitignore`

Before adding files, you must ensure you don't upload your virtual environment or temporary files. If you don't have a `.gitignore` file yet, create one:

Bash

```
touch .gitignore
```

Open that file and add these essential lines for a `uv` project:

Plaintext

```
.venv/
__pycache__/
*.pyc
.python-version
```

### 3. Add and Commit your files

Now, stage your project files and create your first "save point."

Bash

```
git add .
git commit -m "Initial commit: uv project structure"
```

### 4. Create the Repository on GitHub
1. Go to [github.com/new](https://github.com/new).
2. Give it a name (e.g., `my-uv-project`).
3. **Do not** initialize it with a README, license, or gitignore (since we already have them).
4. Click **Create repository**.

### 5. Link and Push

Copy the remote URL from the page that appears and run:

Bash

```
# Link your local folder to GitHub
git remote add origin https://github.com/your-username/your-repo-name.git

# Rename your branch to 'main' (standard practice)
git branch -M main

# Push your code
git push -u origin main
```

### Pro-Tip for `uv` Projects

When someone clones your repo later, they won't need to manually set up an environment. They can simply run:

* `uv sync` to install all dependencies from your `uv.lock` file.
* `uv run python main.py` to run the project instantly.
