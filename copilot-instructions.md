# Soc Ops Copilot Instructions

## Project overview

Soc Ops is a Spring Boot social bingo app for in-person mixers. The app is intentionally lightweight and playable on mobile web. Keep changes focused, production-safe, and easy to reason about.

## Core workflow

- Prefer small, targeted UI updates over large rewrites.
- Keep game logic in Java service/controller code and presentation in the Thymeleaf view and CSS.
- Preserve the existing client-side contracts in the browser script: DOM IDs, global function hooks, and tile state classes.
- Validate with the project test/build commands before finalizing changes.

## Design guide

### Visual direction

- Keep the interface minimal, calm, and readable.
- Favor a neutral palette: warm whites, stone grays, charcoal, and subtle contrast rather than bright or noisy colors.
- Prioritize clarity and ease of play over decoration.
- Use a restrained amount of whitespace and simple borders to create hierarchy without visual clutter.

### UX principles

- The board must remain easy to scan on a phone in a live social setting.
- Selected tiles should read clearly and immediately without distracting animations.
- Buttons should feel tactile but understated; avoid heavy shadows or loud gradients.
- The win state should feel celebratory but not visually chaotic.

### Implementation constraints

- Preserve the IDs used by the JavaScript: `lobbyView`, `activeView`, `gridContainer`, `bingoBanner`, and `victoryOverlay`.
- Preserve the global hooks: `launchGame()`, `retreatToLobby()`, and `dismissVictoryModal()`.
- Keep the dynamic tile classes used by the board renderer intact, especially `bg-marked`, `border-marked-border`, `bg-amber-200`, `border-amber-400`, `bg-white`, `tile-active`, `bg-accent`, and `accent-active`.
- Prefer utility-based styling in [socops/src/main/resources/static/css/app.css](socops/src/main/resources/static/css/app.css); avoid inline styling unless it is necessary for state toggling.

### Aesthetic tone

- Avoid generic “AI slop” layouts and overused gradients.
- Do not default to loud purple, blue-heavy gradients, or glossy card-heavy design patterns.
- Minimal is a feature: a quiet palette, crisp typography, and purposeful spacing will outperform decorative complexity.

## Validation commands

```bash
cd socops && ./mvnw test
cd socops && ./mvnw verify
cd socops && ./mvnw clean package
```
