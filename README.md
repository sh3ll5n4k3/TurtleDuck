# TurtleDuck: HID‑Based Payload Staging via PowerShell (Authorized Use Only)

> ⚠️ For ethical red teaming, physical security testing, and educational use **only**.  
> Explicit written authorization is required before use.

This repository demonstrates how a **HID injection device** (e.g., USB Rubber Ducky–style keystroke injection) can automate user‑interface interactions on Windows to **stage and execute a payload via PowerShell**, without relying on a secondary USB storage device.

The emphasis is on **physical attack surface awareness**, **endpoint defense validation**, and **operator decision‑making under constraints** (user presence, privilege level), not on exploitation for exploitation’s sake.

---

## 💼 Intended Use Cases

- Authorized red team physical security testing
- Purple team endpoint defense validation
- Demonstrating HID trust risks to stakeholders
- User‑presence vs. execution feasibility analysis
- Detection and response tabletop exercises

---

## 📋 What It Does (High‑Level)

1. Invokes Windows Security (Defender) via a system URI.
2. Demonstrates GUI automation concepts and their fragility (requires appropriate privileges).
3. Launches a PowerShell session.
4. Stages a payload by retrieving it from a **remote HTTPS source**.
5. Writes the payload to the **current user’s temporary directory**.
6. Executes the staged payload from disk.

> **Note:** Behavior and outcomes depend on user privilege, Defender configuration, and user presence. This project intentionally highlights those constraints.

---

## 🖱 Trigger Mechanism

A HID device injects keystrokes defined in `payload.txt`.  
This project does **not** require a secondary USB drive for payload execution.

---

## 📁 Repository Contents

- `payload.txt` — HID keystroke payload
- `README.md` — Documentation

---

## ⚙️ Operational Notes

- The payload is **disk‑backed** (written to the user’s temp directory).
- Endpoint protection may block staging or execution depending on policy.
- GUI‑driven approaches are **inherently fragile** and sensitive to OS/UI changes.
- When a user is present and attentive, visible UI interactions are a limiting factor.

---

## 🧭 Scope & Ethics

- Do **not** use on systems you do not own or lack explicit authorization to test.
- This repository is intended for **learning, validation, and reporting**, including documenting **prevented** actions as successful defensive outcomes.

---

## 🔧 Customization (Conceptual)

- Remote source location, payload name, and timing are configurable within the HID script.
- Any changes should remain within authorized scope and be documented for reporting.

---

## 📌 Disclaimer

This project is provided for **defensive security education and authorized testing only**.  
The author(s) assume no responsibility for misuse.
