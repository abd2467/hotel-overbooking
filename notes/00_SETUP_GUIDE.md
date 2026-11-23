# Setup guide (Day 1, Step 1)

How this project was set up on a Mac, what each command does, and why.

## 1. What was done for me
Claude created the GitHub repo `abd2467/hotel-overbooking` (public) through the browser, then added the folder structure and starter files and pushed them. Logged in `AI_USE.md`.

## 2. Commands I ran, line by line

```bash
git clone https://github.com/abd2467/hotel-overbooking.git
```
**What:** downloads a full copy of the repo from GitHub to my laptop, including its history.
**Why:** GitHub is the shared master copy; my laptop needs a working copy to run code.

```bash
cd hotel-overbooking
```
**What:** moves the terminal into the project folder.
**Why:** every later command (venv, pip, git) acts on the folder I am in.

```bash
python3 --version
```
**What:** prints the installed Python version (mine: 3.15.2).
**Why:** confirms Python exists and is new enough. On a Mac, Python 3 is called `python3`; plain `python` does not exist until a virtual environment is active.

```bash
python3 -m venv .venv
```
**What:** creates a private copy of Python inside a hidden `.venv` folder in the project.
**Why:** libraries installed here cannot clash with other projects. `.venv` is in `.gitignore`, so it never goes to GitHub; anyone can rebuild it from `requirements.txt`.

```bash
source .venv/bin/activate
```
**What:** switches this terminal to the project's private Python. The prompt now starts with `(.venv)`, and `python` / `pip` point to the project copy.
**Why:** without this, `pip install` would put libraries in the system Python.
**Remember:** run it every time I open a new terminal for this project. Forgetting it causes "ModuleNotFoundError".

```bash
pip install -r requirements.txt
```
**What:** reads the list of libraries in `requirements.txt` and installs them into `.venv`.
**Why:** one command gives anyone the same toolkit. Installed: pandas 2.3.3, duckdb 2.0.1, lifelines 0.30.3, scikit-learn 1.8.1, scipy 1.18.1, matplotlib 3.11.2, streamlit 1.67.0, jupyter.

## 3. Daily routine
```bash
cd ~/hotel-overbooking        # go to the project (adjust the path if it lives elsewhere)
source .venv/bin/activate     # switch on the project Python
git pull                      # get any changes pushed from elsewhere
```
To switch the project Python off: `deactivate`.

## 4. Mistakes I hit and what they taught me
| Error | Cause | Fix / lesson |
|---|---|---|
| `zsh: command not found: python` | macOS ships `python3`, not `python` | Use `python3` until the venv is active |
| `zsh: command not found: #` | zsh does not treat pasted `#` lines as comments | Harmless; paste commands without comment lines |

## 5. What each starter file is for
| File | Purpose |
|---|---|
| `.gitignore` | Keeps raw data, `.venv`, caches and secrets out of Git |
| `AGENTS.md` / `CLAUDE.md` | Standing rules for any coding agent working in this repo |
| `README.md` | Front page: the decision and result go at the top |
| `DATA_REGISTER.md` | Dataset source, citation, licence, download date |
| `AI_USE.md` | Every AI tool used, what I checked, what I rejected |
| `requirements.txt` | Library list for reproducing the environment |
| `notes/` | Learning log, this guide, the project map |
