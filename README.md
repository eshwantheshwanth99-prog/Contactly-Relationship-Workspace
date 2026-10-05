# Contactly — Your people, thoughtfully organized

A first-year internship project built with C++ and SQLite, expanded into a local relationship workspace with a responsive lavender interface.

## Download and run
The complete source tree is in [Contactly-source.zip](Contactly-source.zip). Download and extract it, then open the Contactly-Relationship-Workspace folder in VS Code.

On macOS, run START-WEBSITE.command from the extracted folder. It builds the server and opens localhost:8080. Apple Command Line Tools and SQLite development libraries are required. Keep the folder and terminal open while using the app.

Manual build (macOS/Linux):
```sh
mkdir -p build
c++ -std=c++17 -Wall -Wextra -Wpedantic -Iinclude optional-web/server.cpp src/contact_core.cpp src/database.cpp -lsqlite3 -o build/contact_web
./build/contact_web contacts.db 8082 optional-web/web
```
Then open http://localhost:8082 on your own computer. This is a source release, not a hosted live demo.

## Features
- Persistent contact CRUD with shared C++ validation and SQLite storage.
- Saved circles, favorites and relationship notes.
- Follow-up queue, next follow-up and last-connected dates.
- Explainable contact completeness insights and missing-details view.
- Instant search across contact details and notes.
- Card and compact layouts, responsive styles, keyboard search shortcut and CSV export.
- The original C++11 console application remains separate from the optional C++17 web adapter.

## Verification and scope
71 automated checks passed: 12 core, 20 database and 39 HTTP checks. JavaScript syntax and HTML/CSS/JS/API asset checks also passed. Read [UPGRADE_REPORT.md](UPGRADE_REPORT.md) for details and limitations.

This is a local, single-user educational project. It has no authentication or cloud sync and sends no automated messages or notifications. Browser interaction verification remains pending; automated tests do not guarantee an internship grade or the absence of all bugs.

The package excludes personal contact databases, credentials, compiled binaries and installed dependencies. A fresh local database is created on first launch.
