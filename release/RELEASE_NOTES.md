# StarFab Extract v0.1.1 — install detection fixes

Bug-fix release that drastically improves Star Citizen install detection.

## Fixes

- **Detects custom install paths** like `C:\GIOCHI\StarCitizen\LIVE`, `D:\Games\StarCitizen\LIVE`, `E:\StarCitizen\LIVE`, etc. — anywhere on any fixed drive that uses a common parent folder name (`Games`, `Giochi`, `Jeux`, `Spiele`, `Juegos`, `Programmi`, `Program Files`, `RSI`, …) or sits at the drive root.
- **Custom P4K setting now actually works.** The path you set in Settings → Paths is forwarded to the detector and shows up in the install list immediately after saving (no app restart needed).
- More robust RSI Launcher `settings.json` parsing — handles the multiple schemas the launcher has shipped.
- Build script no longer aborts on benign pip stderr warnings.

## Workaround for older v0.1.0 users

If you're on v0.1.0 and your install isn't auto-detected, open
**Settings → Paths**, set **Custom P4K** to your `Data.p4k`, and click
**Save**. (In v0.1.0 you also have to restart the app.)

## Downloads

| File | Description |
|------|-------------|
| `StarFabExtract-0.1.1-windows-amd64-installer.exe` | NSIS installer (recommended) |
| `StarFabExtract-0.1.1-windows-amd64.exe` | Portable executable |

## SHA-256

```
8725FB6591D8BB91FD47617A9183CB3CA55FF6F5DF82CF3E0FAC52E99AAA4BB4  StarFabExtract-0.1.1-windows-amd64-installer.exe
C1233DD3E2021532DF4DBD80CD110D3626A8B641F938877FF8B2DC74BF355F7C  StarFabExtract-0.1.1-windows-amd64.exe
```
