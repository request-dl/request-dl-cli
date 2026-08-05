# request-dl-cli

A standalone Swift package: a terminal tool built on top of [`RequestDL`](https://github.com/request-dl/request-dl-nio), with its own curl-familiar flag surface (`--url`, `--header`, `-X`, `-d`, ...) rather than parsing actual `curl` command-line syntax.

## Our goal

Provide a command-line HTTP client that builds entirely on `RequestDL`'s existing public API — no library changes required — covering everything from basic requests to more advanced capabilities:

- Full request support (`--url`, `-X`, `-H`, `-d`, `--query`, `-o`, `-i`)
- Checksum verification (`--checksum sha256:<hex>`)
- Segmented/parallel downloads (concurrent ranged requests)
- Resume-on-interruption for downloads
- Concurrent download queue
- Bandwidth throttling

BitTorrent support was evaluated and is **not recommended**: it's an entirely separate peer-to-peer protocol stack, outside the scope of an HTTP CLI tool.

See the full survey in [`proposals-triage/REPORT.md`](proposals-triage/REPORT.md).
