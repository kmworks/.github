<div align="center">
  <img src="https://raw.githubusercontent.com/kmworks/kmreader/main/icon.svg" alt="KMReader icon" width="96">

  # kmworks

  A Komga-compatible comic/manga reading stack: Rust server, web UI, native Apple client.
</div>

| Project | What it is | Latest |
| --- | --- | --- |
| [kmrs](https://github.com/kmworks/kmrs) | Drop-in, API-compatible reimplementation of the [Komga](https://komga.org) server in Rust — single static binary, no JVM | [![release](https://img.shields.io/github/v/release/kmworks/kmrs)](https://github.com/kmworks/kmrs/releases/latest) [![image](https://img.shields.io/badge/ghcr.io-kmworks%2Fkmrs-blue)](https://github.com/kmworks/kmrs/pkgs/container/kmrs) |
| [kmweb](https://github.com/kmworks/kmweb) | Web UI for kmrs — bundled in the kmrs docker image | [![release](https://img.shields.io/github/v/release/kmworks/kmweb)](https://github.com/kmworks/kmweb/releases/latest) |
| [kmreader](https://github.com/kmworks/kmreader) | Full-featured, native Komga client for iOS, macOS, and tvOS | [![release](https://img.shields.io/github/v/release/kmworks/kmreader)](https://github.com/kmworks/kmreader/releases/latest) [![App Store](https://tools.applemediaservices.com/api/badges/download-on-the-app-store/black/en-us)](https://apps.apple.com/app/id6755198424) |

## Try it

```sh
docker run -d \
  --name=kmrs \
  -p 25600:25600 \
  --mount type=bind,source=/path/to/config,target=/config \
  --mount type=bind,source=/path/to/data,target=/data \
  --restart unless-stopped \
  ghcr.io/kmworks/kmrs
```

Open `http://localhost:25600` — kmweb is bundled and works out of the box — or point any Komga-compatible client at the server.

kmrs pairs well with any Komga-compatible client; kmreader pairs with any Komga-compatible server, including the original [komga](https://github.com/gotson/komga).

Not affiliated with the komga project.
