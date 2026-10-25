# english-listen

Fossify listen player OTA update channel (jsDelivr CDN + version-code probing).

Each release adds two write-once files (never modified, so CDN caches stay correct):

- `fossify-listen-<versionCode>.json` - metadata (versionName / apkUrl / notes)
- `fossify-listen-v<versionName>.apk` - the installer (only the newest 3 are kept)

The app probes codes from its own versionCode+1 upward (max 50, in parallel) and
installs the highest one found; all 404 = already latest. Base URL:

    https://cdn.jsdelivr.net/gh/MTanks/english-listen@main/
