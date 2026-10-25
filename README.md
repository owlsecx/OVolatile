# 🦉 Ovolatile

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OwlSec-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **Ovolatile** — Ovolatile — OwlSec security tool

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview


OVolatile is a volatile-memory and live-forensics tool that captures and inspects transient system state such as running processes, network connections, loaded modules and open handles. It snapshots live host artifacts for incident response and preserves them for analysis. It runs as a desktop application for authorized forensic work.

---

## ✨ Features


- Capture of volatile artifacts: processes, network connections, loaded modules and open files
- Point-in-time live-state snapshots for incident response
- Process and connection detail inspection
- Preservation/export of captured artifacts for later analysis
- Uses psutil for live host data where available
- Desktop UI in the OWLSec theme with an offline --self-test

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage


```bash
./OVolatile
./OVolatile --self-test
./OVolatile --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
