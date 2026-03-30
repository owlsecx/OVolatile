# 🦉 OVolatile

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux%20%2F%20Windows%20%2F%20macOS-informational?style=flat-square&logo=linux&logoColor=white&color=0a0c10"/>
  <img src="https://img.shields.io/badge/Category-OForensics-yellow?style=flat-square"/>
  <img src="https://img.shields.io/badge/Requires-Volatility%203-blueviolet?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-2.0-cyan?style=flat-square"/>
</p>

> **OVolatile** is an interactive Volatility 3 memory forensics wrapper — browse and run 55+ plugins, execute triage batch sets, stream colourised output, and export per-plugin TXT and JSON reports from a clean terminal menu.

---

> ⚠️ **AUTHORISED FORENSIC USE ONLY**

---

## 📌 Overview

OVolatile provides a structured interface over `vol` / `vol3`, removing the need to memorise plugin strings or flags. Every plugin run is streamed live in the terminal with colourised output, saved to disk automatically, and recorded in session history for later review and export.

---

## 🖥️ Menu

| Option | Description |
|--------|-------------|
| **[1] Run Plugin** | Type any plugin name and optional extra arguments — output streams live |
| **[2] Browse Plugins** | Filter by OS group, search by keyword, pick by number |
| **[3] Batch Run** | Enter multiple plugins manually or select a quick triage set |
| **[4] History** | View all previous plugin runs with plugin name, lines, return code, and errors |
| **[5] Export** | Save full session history to a single JSON file |
| **[6] Analysis Guide** | Recommended plugin flow per OS (Linux / Windows / macOS) |
| **[7] Settings** | Set vol binary path, memory dump path, output directory, TXT/JSON toggles, line cap |

---

## 🔌 Plugin Library — 55+ Plugins

### General (3)
`banners.Banners` · `isfinfo.IsfInfo` · `layerwriter.LayerWriter`

### Linux (18)
`pslist` · `pstree` · `psscan` · `bash` · `netstat` · `sockstat` · `lsof` · `malfind` · `ifconfig` · `envars` · `elfs` · `mount` · `kmsg` · `check_modules` · `check_afinfo` · `check_creds` · `check_idt` · `tty_check`

### Windows (22)
`pslist` · `pstree` · `psscan` · `cmdline` · `netscan` · `netstat` · `malfind` · `dlllist` · `handles` · `modules` · `driverscan` · `svcscan` · `ssdt` · `callbacks` · `hashdump` · `lsadump` · `filescan` · `dumpfiles` · `memmap` · `privileges` · `userassist` · `registry.hivelist` · `registry.printkey` · `envars`

### macOS (10)
`pslist` · `pstree` · `bash` · `netstat` · `lsof` · `malfind` · `ifconfig` · `mount` · `check_syscall` · `check_trap_table`

---

## ⚡ Batch Quick Sets

Three built-in triage sets for fast incident response:

| Set | Plugins |
|-----|---------|
| **Linux Triage** | banners → pslist → bash → netstat → malfind |
| **Windows Triage** | banners → pslist → cmdline → netscan → malfind → hashdump |
| **macOS Triage** | banners → pslist → bash → netstat → malfind |

---

## 🗺️ Analysis Guide

Built-in recommended analysis flows accessible from **[6] Analysis Guide**:

**Linux Flow (12 steps)**
banners → pslist → pstree → bash → netstat → sockstat → lsof → malfind → check_modules → check_idt → envars → elfs

**Windows Flow (17 steps)**
banners → pslist → pstree → cmdline → netscan → malfind → dlllist → handles → svcscan → modules → driverscan → ssdt → callbacks → hashdump → lsadump → registry hivelist → filescan

**macOS Flow (8 steps)**
banners → pslist → bash → netstat → lsof → malfind → check_syscall → check_trap_table

---

## 📤 Output Files

Each plugin run saves to `ovolatile_results/` automatically:

| Format | Filename | Contents |
|--------|----------|----------|
| **TXT** | `ovolatile_<plugin>_<timestamp>.txt` | Full plain-text output with header (plugin, memory path, command, return code) |
| **JSON** | `ovolatile_<plugin>_<timestamp>.json` | Structured summary: plugin, memory, command, RC, line count, start/end time |
| **Session** | `ovolatile_session_<timestamp>.json` | Full session history with all plugin runs |

Both TXT and JSON can be toggled independently in Settings.

---

## ⚙️ Settings

| Setting | Default | Description |
|---------|---------|-------------|
| **vol binary** | Auto-detected | Searches `vol`, `vol3`, `vol.py`, `volatility3` in `$PATH` |
| **Memory dump** | *(not set)* | Path to `.raw`, `.mem`, `.vmem`, or other dump file |
| **Output dir** | `ovolatile_results/` | Directory for all saved output files |
| **Save TXT** | On | Save plain-text output per run |
| **Save JSON** | On | Save structured JSON summary per run |
| **Max lines** | 5000 | Live output line cap — full output still saved to file |

---

## ⚙️ Requirements

- **Volatility 3** — must be installed and accessible
- **No Python installation needed** — runs as a standalone executable

```bash
# Install Volatility 3 (if needed)
pip install volatility3
# or
git clone https://github.com/volatilityfoundation/volatility3
```

---

## 🚀 Usage

```bash
./OVolatile
```

On first run, use **[7] Settings** to set the memory dump path before running any plugins.

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
