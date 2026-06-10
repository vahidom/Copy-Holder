# Modernization Roadmap

This document describes possible future improvements. These are not part of the current repository hygiene pass.

## Repository and Build

- Migrate from Eclipse/ADT project structure to Gradle.
- Remove generated artifacts from version control.
- Replace vendored JAR files with declared Maven dependencies.
- Add CI for build, lint, and tests.

## Android Platform

- Update the target SDK.
- Migrate from Android Support Library to AndroidX.
- Replace deprecated clipboard and notification APIs.
- Add modern notification channels and explicit `PendingIntent` flags.

## Architecture

- Separate UI, clipboard monitoring, and persistence responsibilities.
- Replace static activity state with lifecycle-aware state management.
- Introduce a repository layer for clipboard entries.
- Consider Room for typed SQLite access and migrations.

## Privacy and Product Behavior

- Redesign clipboard capture around modern Android privacy restrictions.
- Add clear user consent and data retention controls.
- Consider explicit save/share-sheet workflows instead of background clipboard monitoring.
- Disable or restrict backup for sensitive clipboard data.

## Testing

- Add unit tests for database/repository behavior.
- Add instrumentation tests for core UI flows.
- Add lint checks and dependency scanning.
