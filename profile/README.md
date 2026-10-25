<div align="center">
  <img src="https://raw.githubusercontent.com/kmworks/kmreader/main/icon.svg" alt="KMReader icon" width="96">

  # kmworks

  An open-source, Komga-compatible reading stack for comics, manga, and ebooks: a Rust server with a built-in web UI, and a native Apple client.

  [Website](https://kmworks.date) · [Docs](https://kmworks.date/server/intro) · [Live demo](https://demo.kmworks.date) · [Blog](https://kmworks.date/blog/)
</div>

| Project | What it is | Latest |
| --- | --- | --- |
| [KMServer](https://github.com/kmworks/kmrs) (`kmrs`) | Full-featured drop-in replacement for the [Komga](https://komga.org) server in Rust — same library formats, API, and database, plus smart lists, reading trackers, CJK search, and more. One self-contained binary with the web UI built in, no JVM | [![release](https://img.shields.io/github/v/release/kmworks/kmrs)](https://github.com/kmworks/kmrs/releases/latest) [![image](https://img.shields.io/badge/ghcr.io-kmworks%2Fkmrs-blue)](https://github.com/kmworks/kmrs/pkgs/container/kmrs) |
| [KMReader](https://github.com/kmworks/kmreader) | Native Komga client for iPhone, iPad, Mac, and Apple TV, with offline downloads and on-device manga translation | [![release](https://img.shields.io/github/v/release/kmworks/kmreader)](https://github.com/kmworks/kmreader/releases/latest) [![App Store](https://tools.applemediaservices.com/api/badges/download-on-the-app-store/black/en-us)](https://apps.apple.com/app/id6755198424) |

## Try it

```sh
docker run -d \
  --name=kmrs \
  --user 1000:1000 \
  -p 25600:25600 \
  --mount type=bind,source=/path/to/config,target=/config \
  --mount type=bind,source=/path/to/data,target=/data \
  --restart unless-stopped \
  ghcr.io/kmworks/kmrs
```

Open `http://localhost:25600` — the web UI is built in — or point any Komga-compatible client at the server. Prebuilt binaries for Linux, macOS, and Windows are on the [releases page](https://github.com/kmworks/kmrs/releases/latest).

Already running Komga? Point KMServer at your existing config directory and it upgrades the database in place; the [migration guide](https://kmworks.date/server/migration) covers the switch, and the Java version can still open the result.

KMServer works with any Komga-compatible client, and KMReader works with any Komga 1.20.0+ server, including the original [Komga](https://github.com/gotson/komga).

All kmworks projects are MIT licensed. Not affiliated with the Komga project.
