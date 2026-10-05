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

Without admin rights, from a terminal:

```powershell
# Windows
irm https://github.com/VectorSophie/a3v-releases/releases/latest/download/a3v-installer.ps1 | iex
```

```bash
# macOS / Linux
curl --proto '=https' --tlsv1.2 -LsSf https://github.com/VectorSophie/a3v-releases/releases/latest/download/a3v-installer.sh | sh
```

After installing, run `a3v setup` to configure A3V (the MSI and pkg run it for you), and `a3v demo` to try it.

Release builds are not yet code-signed, so Windows SmartScreen and macOS Gatekeeper will warn before the first run. The MSI installs machine-wide and asks for administrator approval.

## Verify

Check a download before running it. The archives and the MSI are listed in `sha256.sum`; the `.pkg`, `.deb` and `.rpm` each have their own `.sha256` file next to them.

```bash
sha256sum -c sha256.sum --ignore-missing                  # archives, MSI
sha256sum -c a3v_<version>-1_amd64.deb.sha256              # a single package
```

```powershell
# Windows: compare with the matching .sha256 file
(Get-FileHash a3v-x86_64-pc-windows-msvc.msi -Algorithm SHA256).Hash.ToLower()
```

## License

MIT. See [LICENSE](LICENSE).
