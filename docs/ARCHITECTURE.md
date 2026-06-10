# Architecture Overview

Copy Holder uses a compact legacy Android architecture with activities, a background service, and a SQLite helper.

## Main Components

- `MainActivity`: displays clipboard history, provides search, and handles entry actions such as edit, delete, copy, and share.
- `Edit`: allows editing a selected clipboard entry.
- `Holdservice`: monitors clipboard changes and stores new text entries.
- `database`: copies the bundled SQLite database from assets and provides basic create, read, update, and delete operations.

## Data Flow

1. The user enables clipboard monitoring in the main screen.
2. The service listens for clipboard changes.
3. New clipboard text is checked against the SQLite database.
4. Unique entries are inserted into the `copytable` table.
5. The main screen loads entries from SQLite and displays them in a list.
6. Users can edit, delete, copy, share, or search saved entries.

## Persistence

The app includes a prebuilt SQLite database in `assets/copydata`. At runtime, the database helper copies this asset into the app database directory if it does not already exist.

The schema contains a `copytable` table with an auto-incrementing `id` and text field `cdata`.

## Legacy Constraints

The implementation uses static UI state, deprecated Android APIs, and direct coupling between the database helper and activity state. These patterns were common in small Android projects of the era but would be refactored in a modern version.
