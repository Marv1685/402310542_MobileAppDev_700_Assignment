# Smart Pantry Manager

An Android app (Java) that reduces food waste. You record the ingredients you have at home, and the app suggests only the recipes you can cook **right now** - a recipe appears only if *every* ingredient is in your pantry in at least the required quantity.

## Features
- Add / edit / delete pantry items (name, quantity, unit, optional expiry date) with input validation
- Pantry list (RecyclerView + custom adapter) backed by a database
- 18 pre-loaded recipes (seeded on first run)
- Suggested Recipes screen with strict matching (handles plurals like tomato/tomatoes and unit differences like kg/g)
- Recipe detail screen, empty-state message, Settings screen (expiring-soon alerts), bottom navigation

## Database choice: SQLite via Room
(Edit in your own words.) Room is a local, offline database with compile-time checked queries and no backend to host. Data is stored in the app's private storage, so it persists after the app is closed and reopened.

## Setup / run
1. Install Android Studio with the Android SDK (API 36).
2. File > Open this folder and wait for Gradle sync (internet needed the first time).
3. Run on an emulator or a phone (Android 7.0 / API 24 or newer).

## Structure
- `data/` - Room entities, DAOs, database, seed data
- `logic/` - `Normalizer` and `RecipeMatcher` (the strict-matching rule)
- root package - Activities and adapters
- `src/test` - unit tests for the matching rule

No maps, location or GPS features are used.
