# Awesome Skink [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of awesome [Skink](https://github.com/markoxley/skink) frameworks, libraries and software.

Inspired by [awesome-go](https://github.com/avelino/awesome-go). All modules are installed with [scales](https://github.com/markoxley/skink/tree/main/tools/scales), the Skink package manager:

```bash
scales init                                # once: create skink.toml
scales add mod/markoxley/<repo>[@version]  # fetch into the scales cache
```

then `import "mod/markoxley/<repo>"` in your sources.

## Contents

- [Awesome Skink ](#awesome-skink-)
  - [Contents](#contents)
  - [Database](#database)
  - [Web](#web)
  - [AI \& NLP](#ai--nlp)
  - [Multimedia](#multimedia)
  - [Game Development](#game-development)
  - [GUI](#gui)
  - [Configuration](#configuration)
  - [Development Tools](#development-tools)
  - [Contributing](#contributing)
  - [License](#license)

## Database

*Drivers, abstraction layers, and ORMs for connecting and operating databases.*

- [skink-dbx](https://github.com/markoxley/skink-dbx) — Shared database-driver core: connection vtables, DSN parsing, buffered/TLS connections, SCRAM auth, value model, and connection pooling.
- [skink-postgres](https://github.com/markoxley/skink-postgres) — PostgreSQL driver: pure-Skink v3 wire protocol, cleartext/MD5/SCRAM-SHA-256 auth, simple + extended query, TLS, dbx adapter.
- [skink-mysql](https://github.com/markoxley/skink-mysql) — MySQL/MariaDB driver: pure-Skink wire protocol (packets, lenenc), `mysql_native_password` + `caching_sha2_password` auth, COM_QUERY + prepared statements, TLS, dbx adapter.
- [skink-mssql](https://github.com/markoxley/skink-mssql) — Microsoft SQL Server driver: pure-Skink TDS 7.x (PRELOGIN, LOGIN7, SQLBatch, `sp_executesql` params, token streams), TLS negotiation, transactions, dbx adapter.
- [skink-mongo](https://github.com/markoxley/skink-mongo) — MongoDB driver: pure-Skink BSON codec + OP_MSG wire protocol, SCRAM-SHA-1/SHA-256 auth, CRUD with cursors, dbx adapter.
- [skink-redis](https://github.com/markoxley/skink-redis) — Redis client: RESP2/RESP3 wire codec, typed commands, pipelining, pub/sub, TLS (`rediss://`), dbx adapter.
- [skink-tegu](https://github.com/markoxley/skink-tegu) — Database-agnostic ORM: dialect-aware SQL builder, struct↔table mapping, joins, eager relations, migrations, transactions — over dbx drivers and SQLite.

## Web

*Frameworks and libraries for building web applications and services.*

- [skink-zilla](https://github.com/markoxley/skink-zilla) — Fiber-style web framework: app/ctx, routing groups, JWT, sessions, authorization, rate limiting, CORS, multipart uploads, WebSocket — over `std/web`.

## AI & NLP

*Speech, language, and ML-adjacent tooling.*

- [skink-vox](https://github.com/markoxley/skink-vox) — NLP module for Skink.
- [skink-stt](https://github.com/markoxley/skink-stt) — Speech-to-text: pluggable provider interface, OpenAI-compatible REST transcription (multipart upload), whisper.cpp and generic subprocess providers.
- [skink-tts](https://github.com/markoxley/skink-tts) — Text-to-speech: pluggable provider interface, OpenAI-compatible REST provider, espeak/piper/say subprocess providers.

## Multimedia

*Audio, image, and computer vision libraries.*

- [skink-audio](https://github.com/markoxley/skink-audio) — PCM/WAV audio: DSP (gain/mix/filters/resample), FFT spectrum analysis, oscillators + ADSR synthesis, subprocess playback (aplay/paplay/ffplay/afplay).
- [skink-cv](https://github.com/markoxley/skink-cv) — Computer vision: pure-Skink image core (PNG/BMP/PPM, resize/crop/flip, convolutions, Sobel edges, thresholding, histogram equalization, connected components, Harris corners) plus an optional OpenCV backend in `cv/ocv`.

## Game Development

- [skink-game](https://github.com/markoxley/skink-game) — 2D game toolkit: engine core (entities, fixed-timestep loop, math), pure-Skink ANSI terminal backend, SDL2 backend in `game/sdl`.

## GUI

*Libraries for building native desktop applications.*

- [skink-gnome](https://github.com/markoxley/skink-gnome) — GNOME desktop apps in pure Skink: GTK 4 widgets (windows, header bars, entries, menus/`GAction`s, GLib main loop) plus libadwaita (`AdwApplicationWindow`, toasts, banners, preference rows, alert dialogs, dark mode) — no C shim.

## Configuration

- [skink-nest](https://github.com/markoxley/skink-nest) — Configuration management for Skink.

## Development Tools

*Official compiler tools — part of the main [skink](https://github.com/markoxley/skink) repository.*

- [scales](https://github.com/markoxley/skink/tree/main/tools/scales) — Package manager: `scales init/add/install`, `skink.toml`/`skink.lock`, `mod/<owner>/<repo>[@version]` imports.
- [skinkfmt](https://github.com/markoxley/skink/tree/main/tools/skink-lsp) — Source formatter (built alongside `skink-lsp` from `tools/skink-lsp`).
- [skink-lsp](https://github.com/markoxley/skink/tree/main/tools/skink-lsp) — Language server for editor integration (VS Code extension available).
- [skinkjs](https://github.com/markoxley/skink/tree/main/tools/skinkjs) — Skink → ECMAScript/JavaScript backend.
- [skinkcov](https://github.com/markoxley/skink/tree/main/tools/skinkcov) — Coverage reporter for `skink -cov` instrumented builds.

## Contributing

New modules are published as `mod/<owner>/<repo>` packages discoverable by `scales`. To propose an addition or update to this list, open a pull request.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)
