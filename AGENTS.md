---
description: Context and conventions for working on the Soc Ops Social Bingo application.
---

# Soc Ops — Agent Development Guide

**Soc Ops** is a Spring Boot social bingo game application designed for in-person mixers. This guide helps AI agents understand the codebase, conventions, and workflows for productive development.

## Mandatory Development Checklist

Complete all items before opening or merging a PR:

- [ ] Lint: `cd socops && ./mvnw verify`
- [ ] Build: `cd socops && ./mvnw clean package`
- [ ] Test: `cd socops && ./mvnw test`

## Quick Reference

### Core Commands
```bash
# Start dev server (auto-reload)
cd socops && ./mvnw spring-boot:run

# Build artifact + tests
cd socops && ./mvnw clean package

# Tests only
cd socops && ./mvnw test
```

### Project Map
```text
socops/
├── src/main/java/com/socops/
│   ├── web/BingoRestController.java
│   ├── service/BoardAssembler.java
│   ├── data/IcebreakerPrompts.java
│   └── model/{BingoCell,PlayPhase,WinningStreak}.java
├── src/main/resources/
│   ├── templates/game.html
│   └── static/css/app.css
└── src/test/java/com/socops/service/BoardAssemblerTests.java
```

## Architecture Snapshot

- **Controller:** [BingoRestController.java](socops/src/main/java/com/socops/web/BingoRestController.java) serves `/` and `/api/bingo/fresh-board`.
- **Service:** [BoardAssembler.java](socops/src/main/java/com/socops/service/BoardAssembler.java) builds a shuffled 5x5 board with a fixed center free space.
- **Data:** [IcebreakerPrompts.java](socops/src/main/java/com/socops/data/IcebreakerPrompts.java) stores the prompt catalog.
- **UI:** [game.html](socops/src/main/resources/templates/game.html) + [app.css](socops/src/main/resources/static/css/app.css).

## Common Tasks

### Add or Update Prompts
1. Edit [IcebreakerPrompts.java](socops/src/main/java/com/socops/data/IcebreakerPrompts.java).
2. Keep the playable prompt count at 24 (center is free).
3. Run tests.

### Change Board Rules
Edit [BoardAssembler.java](socops/src/main/java/com/socops/service/BoardAssembler.java) for selection, shuffle, or free-space behavior.

### Redesign Frontend
1. Update structure in [game.html](socops/src/main/resources/templates/game.html).
2. Update utilities/styles in [app.css](socops/src/main/resources/static/css/app.css).
3. Validate in `spring-boot:run` at `http://localhost:8080`.

## Agent Shortcuts

- `pixel-jam`: UI/UX design iteration
- `quiz-master`: prompt/content generation
- `tdd-red` -> `tdd-green` -> `tdd-refactor`: full TDD cycle
- `ui-review`: UX quality review

## Conventions

- Java packages use `com.socops.{web,service,model,data}`.
- Keep HTTP logic in controller and game logic in services.
- Prefer utility classes in [app.css](socops/src/main/resources/static/css/app.css); avoid inline styles.
- Default branch is `main`; PR template lives in `.github/`.

## Related Docs

- [workshop/GUIDE.md](workshop/GUIDE.md)
- [CONTRIBUTING.md](CONTRIBUTING.md)
- [README.pt_BR.md](README.pt_BR.md)
- [README.es.md](README.es.md)

---

**Last Updated:** 2026-08-25 | For issues or contributions, see [CONTRIBUTING.md](CONTRIBUTING.md)
