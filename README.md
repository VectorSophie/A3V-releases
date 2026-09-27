<h1 align="center">A3V releases</h1>

<p align="center">
  Installers, binaries and checksums for <b>A3V</b> (Agent Attack &amp; Abuse Adversarial Vaccine):
  security benchmarking and runtime protection for AI coding agents.
</p>

---

This repository holds **release artifacts only**. A3V's source is developed in a private repository; every release here is built and published by that repository's CI.

## Install

Starting with **v2.4.0**, each [release](https://github.com/VectorSophie/a3v-releases/releases) provides:

| Platform | Artifact |
|---|---|
| Windows x86_64 | `.msi` installer (options page, silent install via `msiexec /qn`) and `a3v-installer.ps1` |
| macOS (Apple silicon + Intel) | `.pkg` installer and `a3v-installer.sh` |
| Linux x86_64 | `.deb`, `.rpm` and `a3v-installer.sh` |
| All | Plain archives and `sha256.sum` |

After installing, run `a3v setup` to configure A3V, and `a3v demo` to try it.

## Verify

Every artifact is listed in the release's `sha256.sum`. Check a download before running it:

```bash
sha256sum -c sha256.sum --ignore-missing
```

## License

MIT. See [LICENSE](LICENSE).
