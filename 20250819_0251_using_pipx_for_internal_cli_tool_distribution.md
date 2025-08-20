### 🧰 `pipx` vs `pip`

- `pip` installs packages into the **current Python environment**, useful for libraries and dependencies.
- `pipx` installs **CLI tools** in **isolated virtual environments**, one per tool.
- Tools installed via `pipx` are linked globally (`~/.local/bin/`), and their environments are stored under `~/.local/pipx/venvs/`.

---

### ⚙️ Python Version Used by `pipx`

- `pipx` uses the **Python interpreter it was installed with**.
- You can check this using:
  ```bash
  pipx runpython --version
  ```
- To override Python version per install:
  ```bash
  pipx install foo --python python3.9
  ```

---

### 📦 Per-Tool Isolation

- Each `pipx install` creates its **own virtualenv**.
- Example:
  ```bash
  pipx install foo
  pipx install bar
  ```
  This creates:
  - `~/.local/pipx/venvs/foo/`
  - `~/.local/pipx/venvs/bar/`

---

### ❌ `pipx install -e .` is NOT for dev workflows

- Avoid using `pipx` for installing editable local projects.
- For dev:
  ```bash
  python -m venv .venv
  source .venv/bin/activate
  pip install -e .
  ```

---

### ✅ Using `pipx` for Internal CLI Tools

- Perfect for distributing tools to teammates who don't want to manage Python or venvs.
- Install from a subdirectory in Git repo:
  ```bash
  pipx install "git+https://your.repo.url/repo.git@branch#subdirectory=path/to/cli"
  ```

---

### 🔄 Updates and Cleanup

- To update a tool:
  ```bash
  pipx upgrade mycli
  ```
- To reinstall cleanly:
  ```bash
  pipx reinstall mycli
  ```
- To uninstall:
  ```bash
  pipx uninstall mycli
  ```
- No zombie venvs are left behind in normal use.

---

### 🧪 Real Example

Internal CLI tool living at:
```
https://gitlaba.ttgits.com/tequila/external-proxy/-/blob/develop/tools/modify_ips/pyproject.toml
```

Install with:
```bash
pipx install "git+https://gitlaba.ttgits.com/tequila/external-proxy.git@develop#subdirectory=tools/modify_ips"
```

Uninstall with:
```bash
pipx uninstall modify-ips  # or use the name shown in `pipx list`
```

---

### 📌 Tags

#python #pipx #cli-tools #devtools #internal-tools #zettelkasten
