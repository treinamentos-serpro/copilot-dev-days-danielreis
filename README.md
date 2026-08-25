<div align="center">

# 🎲 Soc Ops

### Social Bingo for In-Person Mixers

**Find people who match the prompts. Mark your card. Get 5 in a row. Win.**

[![Live Demo](https://img.shields.io/badge/🎮_Live_Demo-Play_Now-4f46e5?style=for-the-badge)](https://copilot-dev-days.github.io/agent-lab-java/)
[![Lab Guide](https://img.shields.io/badge/📚_Lab_Guide-Start_Here-16a34a?style=for-the-badge)](workshop/GUIDE.md)

🌐 [Português (BR)](README.pt_BR.md) | [Español](README.es.md)

</div>

---

## What is Soc Ops?

Soc Ops is a **Spring Boot social bingo game** built for GitHub Copilot workshops. Each player gets a unique 5×5 bingo card filled with icebreaker prompts — find someone in the room who matches each cell, mark it off, and race to five in a row.

But Soc Ops is more than a game. It's a **hands-on lab** for learning how to build real features with GitHub Copilot Agents — from context engineering and UI redesign to TDD and multi-agent workflows.

---

## ✨ Highlights

| | |
|---|---|
| 🃏 **Unique boards** | Every player gets a freshly shuffled card |
| 🏆 **Win detection** | Rows, columns, and diagonals — all tracked |
| 🎨 **Themeable UI** | CSS utility system ready for your creative redesign |
| ⚡ **Zero config** | One command to run; deploys to GitHub Pages automatically |
| 🤖 **Agent-ready** | Structured for Copilot Agent development labs |

---

## 🧪 Lab Overview

This repo is the starting point for a **60-minute GitHub Copilot Agent Lab**. You'll use Copilot to build, redesign, and extend Soc Ops — no boilerplate, all real features.

| Part | Title | What you'll do |
|------|-------|----------------|
| [**00**](workshop/00-overview.md) | Overview & Checklist | Get oriented, check prerequisites |
| [**01**](workshop/01-setup.md) | Setup & Context Engineering | Generate workspace instructions, run background agents |
| [**02**](workshop/02-design.md) | Design-First Frontend | Full UI redesign via Plan Mode |
| [**03**](workshop/03-quiz-master.md) | Custom Quiz Master | Generate a themed prompt set with a custom agent |
| [**04**](workshop/04-multi-agent.md) | Multi-Agent Development | TDD cycle + UX review with multi-agent workflows |

📖 **[Open the full Lab Guide →](workshop/GUIDE.md)**

---

## 🚀 Quick Start

**Prerequisites:** [Java 21+](https://adoptium.net/) · [Maven 3.9+](https://maven.apache.org/) (or use the included wrapper)

```bash
# Run the app (auto-reloads on changes)
cd socops && ./mvnw spring-boot:run
```

Open [http://localhost:8080](http://localhost:8080) and start playing.

```bash
# Build & test
cd socops && ./mvnw clean package
cd socops && ./mvnw test
```

> Pushes to `main` deploy automatically to GitHub Pages.

---

## 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines. Questions? Open an issue.
