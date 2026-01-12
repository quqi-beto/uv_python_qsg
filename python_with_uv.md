# Maximizing uv for Python

### Installing multiple Python version
Install and manage multiple Python versions with the command-line tool uv to create isolated project environments, ensure compatibility with different libraries, and facilitate testing across various Platforms.
#### Examples  
  ```powershell
  # Install a specific version
  uv python install 3.12

  # Install multiple versions in one command
  uv python install 3.11 3.10

  # To see all available and installed Python versions
  uv python list

  # To uninstall
  uv python uninstall 3.12
  ```

### Running Scripts

  ```powershell
  # Running a Python script
  uv run main.py

  # Running a script on specific version of Python
  uv run --python 3.12 main.py 

  # Temporarily install specific dependency(request) before running the script
  uv run --with request --python 3.12 main.py
  # or
  uv run --with request, rich --python 3.12 main.py
  # or
  uv run --with "request==13.7.1" --python 3.12 main.py
  ```
### uv initialize a script
declare the python version and dependencies inside the script instead of the command line
  - `uv init --script main.py`
  - then in main.py specify the python version and dependencies required
    ```
    # /// script
    # requires-python = ">=3.12"
    # dependencies = [
    # "request",
    # "rich",
    # ]
    # ///
    ```
  - then run `uv run main.py`
### Initialize a python project
- `uv init myproject`
- `cd myproject`
- this will generate the following files
```
mypropject/
├── .gitignore
├── .python-version
├── main.py
├── pyproject.toml
├── README.md
```
- in the `pyproject.toml` you can specify the python and dependencies required
