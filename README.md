# Arivna Browser releases

Official APK downloads of [Arivna Browser](https://arivna.in/) for Android. This repository holds no source code: only release files and their checksums. Download APKs only from the [Releases tab](https://github.com/viroaryan/arivna-browser-releases/releases) of this repository.

Source code: https://github.com/viroaryan/arivna-browser · Website: https://arivna.in/ · Google Play: coming soon.

## Versions

| Version | Date | Requires | Download | SHA-256 |
|---|---|---|---|---|
| v1.0.0 | 2026-10-24 | Android 8.0+ (minSdk 26) | [Release v1.0.0](https://github.com/viroaryan/arivna-browser-releases/releases/tag/v1.0.0) | `TBD` |

What changed in each version: [CHANGELOG](https://github.com/viroaryan/arivna-browser/blob/HEAD/CHANGELOG.md).

## Download

1. Open the [Releases tab](https://github.com/viroaryan/arivna-browser-releases/releases).
2. Pick a version (the newest is at the top, marked *Latest*).
3. Under **Assets**, download `arivna-browser-vX.Y.Z.apk` and `checksums.txt`.

## Verify the download (SHA-256)

Compute the file's SHA-256 and compare it with the value in `checksums.txt` and in the table above. They must match exactly; if not, delete the file and do not install it.

Windows (PowerShell):

```powershell
Get-FileHash .\arivna-browser-v1.0.0.apk -Algorithm SHA256
```

macOS:

```bash
shasum -a 256 arivna-browser-v1.0.0.apk
```

Linux:

```bash
sha256sum arivna-browser-v1.0.0.apk
# or check against the file directly:
sha256sum -c checksums.txt
```

## Signing

<!-- This sentence must stay true. Once Play App Signing is active, every APK published here must be the universal APK exported from Play Console (App bundle explorer > Downloads > Signed, universal APK), never an APK signed locally with the upload or debug key. -->
Official APKs are signed with the same key as the Google Play version, so you can update between this APK and the Play Store version without uninstalling.

A build you make yourself from source has a different signature: Android will refuse to install it over the official app until you uninstall the official one (which deletes its data).

## Install

1. Open the downloaded APK from your browser's downloads or a file manager.
2. If Android asks, allow **Install unknown apps** for that app (Settings > Apps > Special app access > Install unknown apps). You can turn it off again afterwards.
3. Tap **Install**. To update, install the newer APK over the old one; your data is kept.

Requires Android 8.0 or later on an ARM (64- or 32-bit) or x86_64 device.

## Support

Email **contactus@arivna.com**. Please report security issues there privately, not in public issues.
