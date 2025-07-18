For python file:

1. Installed UV in Windows Powershell Administrator

powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"


2. Under project folder, create a main.py file to know which python version is used


3. To create a new project

uv init 


4. To know what are the available python versions or what is already installed in your operating system

uv python list


5. To install a python version

uv python install [version]


6. To find a python version

uv python find [version]


7. To uninstall a python version

uv python uinstall [version]


8. To run a python script

uv run main.py

For specific python version,

uv run --python 3.13 main.py

For running an import and python version (useful for running scripts with specific version and/or including external packages/dependencies without permanently installing them),

uv run --with rich --python 3.9 main.py


9. To create a script in main.py file

uv init --script main.py --python 3.13


10. To add dependencies in main.py file 

uv add --script main.py "requests"

It can be manually added as long as you know the library name:
# /// script
# requires-python = ">=3.13"
# dependencies = [
#     "requests",
# ] 
# ///


For python projects

1. To create a new project (with other files such as .gitignore, .python-version, main.py, pyproject.toml, README.md),

uv init


2. To put the new project files in a specific directory

uv init [directory folder name]


3. To add dependencies in uv (it automatically creates .venv file if its not existing yet. pyproject.toml is updated and uv.lock is added)

uv add [dependency name]

uv add requests


4. To add dependency with specific version

uv add requests==2.32.3

You can also add dependencies by writing its name and version in pyproject.toml


5. To uninstall a dependency

uv remove [dependency name]

uv remove requests


6. To downgrade python version

Go to pyproject.toml and .python-version and edit the python version


7. To synchronize the virtual environment with dependencies specified in pyproject.toml (including newly added or removed dependencies)

uv sync


8. To generate or update the uv.lock (counterpart in Node is package-json.lock)

uv lock


9. To go back to legacy pip

uv pip


Documentation:

Easier compare to pip because it uninstall the dependency easily and its other related files to that dependency.

https://docs.astral.sh/uv/