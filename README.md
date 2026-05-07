# StarFab Extract

A fast Windows desktop tool for browsing and extracting assets from
**Star Citizen**'s `Data.p4k` archive. Built with **Wails** (Go shell +
Vue 3 UI) and a self-contained Python sidecar — no Python install
required on the target machine.

> ⚠️ Unofficial fan project. Not affiliated with Cloud Imperium Games or
> Roberts Space Industries. Star Citizen® is a registered trademark of
> CIG. Use only with assets from your own legitimate game install.

---

## Download

Latest release: [`v0.1.0`](https://github.com/CrimsonDawnOrg/StarFabExtract-RELEASE/releases/latest)

| File | Description |
|------|-------------|
| `StarFabExtract-0.1.0-windows-amd64-installer.exe` | NSIS installer (recommended). Adds Start Menu entry + auto-update. |
| `StarFabExtract-0.1.0-windows-amd64.exe` | Portable executable. Run from anywhere. |

**System requirements:** Windows 10 / 11 (x64), WebView2 runtime
(pre-installed on Windows 11; auto-installed by the installer on
Windows 10).

---

## Features

### Ship browser
- Auto-detects every Star Citizen install on your machine (LIVE, PTU,
  EPTU, TECH-PREVIEW, custom).
- Browses every flyable ship by manufacturer, role, size and price.
- One-click extract of a ship's complete asset bundle (geometry,
  textures, materials, blueprints, localization).

### Advanced search
- **Three search modes:**
  - **Text** — fuzzy filename matching with `+token / -token` tokens
    (e.g. `mole cargo -proxy`) and `.ext` shortcuts.
  - **Glob** — shell-style patterns (e.g. `ships/*/cockpit*.xml`).
  - **Regex** — full Python regular expressions.
- **Folder tree navigation** — browse the entire P4K hierarchy on the
  left, click any folder to scope the search to it.
- **Extension filter** — multi-select chip filter populated from the
  index (sorted by frequency).
- **Case-sensitive toggle**, breadcrumb-clickable folder scope chip,
  and per-row "scope to this folder" shortcut.
- Index of ~600k entries built once, cached locally and reused until
  the next game patch.

### Extraction
- Multi-file extraction with live per-job progress, ETA and throughput.
- Preserves original P4K folder structure.
- Background job dock — extract while you keep browsing.

### Other
- Dark Star-Citizen-themed UI (indigo/cyan accents on near-black).
- Sticky action bars and keyboard-friendly shortcuts.
- Logs viewer with sidecar diagnostics for troubleshooting.

---

## Installation

### Installer (recommended)
1. Download `StarFabExtract-0.1.0-windows-amd64-installer.exe`.
2. Run it — installs to `%LOCALAPPDATA%\Programs\StarFabExtract` (no
   admin rights needed).
3. Launch from the Start Menu.

### Portable
1. Download `StarFabExtract-0.1.0-windows-amd64.exe`.
2. Place it in any folder and double-click.
3. The Python sidecar is bundled inside the EXE.

---

## First run

1. Open **Settings** and confirm your Star Citizen install path was
   detected correctly. Set a default extraction directory.
2. Open **Search** and click **Scan P4K now** — first scan takes
   1–3 minutes and indexes ~600,000 files. Subsequent launches are
   instant (cached).
3. Open **Ships** to browse and one-click extract complete ships.

---

## Verifying downloads

SHA-256 checksums for v0.1.0:

```
11C9DC76F9556D49B22A634538228842C032AF873BA63EBBF0D271DD786DC395  StarFabExtract-0.1.0-windows-amd64-installer.exe
510BEAEA9AA734A2BA6C84CA63C566D82429C5C36C62CA1D939D86CEFB958B5F  StarFabExtract-0.1.0-windows-amd64.exe
```

Verify in PowerShell:

```powershell
Get-FileHash .\StarFabExtract-0.1.0-windows-amd64-installer.exe -Algorithm SHA256
```

---

## Troubleshooting

- **"App didn't start"** → install the [Microsoft Edge WebView2
  Runtime](https://developer.microsoft.com/microsoft-edge/webview2/).
- **"Sidecar exited"** → open **Logs** and copy the trace into a
  GitHub Issue. Most often this is a corrupted P4K cache —
  click **Rebuild index** in the Search view.
- **Antivirus warning** — the executable is unsigned (no code-signing
  certificate yet). Verify the SHA-256 above and add an exclusion if
  needed.

---

## License

See [`LICENSE`](LICENSE).
