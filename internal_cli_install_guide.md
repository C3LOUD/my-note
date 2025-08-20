# 🛠 Internal CLI Tool Install Guide

## Overview

This tool provides a CLI for modifying IPs used by the internal proxy system. It is distributed via `pipx` to ensure users don't need to manage Python environments manually.

---

## 🚀 Installation

Make sure you have `pipx` installed. Then run:

```bash
pipx install "git+https://gitlaba.ttgits.com/tequila/external-proxy.git@develop#subdirectory=tools/modify_ips"
```

This will:
- Create an isolated environment for the tool
- Make the CLI globally available in your shell (`modify-ips`)

---

## 🔄 Upgrading

To update the tool after a new release:

```bash
pipx upgrade modify-ips
```

---

## 🧹 Uninstalling

To remove the tool completely:

```bash
pipx uninstall modify-ips
```

---

## 🧪 Debugging

To check Python version or environment:

```bash
pipx runpython --version
pipx list
```

---

## 🧷 FAQ

- **Q**: Do I need Python installed?
  - **A**: Yes, but `pipx` handles isolation for you. Just install `pipx` once.
- **Q**: Will this mess up my other Python tools?
  - **A**: No. `pipx` isolates each CLI tool in its own virtual environment.

