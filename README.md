<p align="center"><img src="https://raw.githubusercontent.com/viroaryan/arivna-browser/main/docs/logo.png" alt="Arivna logo" width="96" height="96"></p>

# Arivna Browser releases

Official APK downloads of Arivna Browser for Android. This repository holds no source code: only release files and their checksums. Download APKs only from the [Releases tab](https://github.com/viroaryan/arivna-browser-releases/releases) of this repository.

Source code: https://github.com/viroaryan/arivna-browser · Google Play: coming soon.

## Versions

| Version | Date | Requires | Download | SHA-256 |
|---|---|---|---|---|
| v1.0.1 | 2026-10-25 | Android 8.0+ (minSdk 26) | [Release v1.0.1](https://github.com/viroaryan/arivna-browser-releases/releases/tag/v1.0.1) | `396df2c84122f275c34f49975ad98a9fa39af2899eb2231c64fb7d9b5aa3a415` |
| v1.0.0 | 2026-10-24 | Android 8.0+ (minSdk 26) | [Release v1.0.0](https://github.com/viroaryan/arivna-browser-releases/releases/tag/v1.0.0) | `050c18063aa6c916107d18bf508152f76a42e7ae4e13ce725474c180ab5819b5` |

What changed in each version: [CHANGELOG](https://github.com/viroaryan/arivna-browser/blob/HEAD/CHANGELOG.md).

## Download

1. Open the [Releases tab](https://github.com/viroaryan/arivna-browser-releases/releases).
2. Pick a version (the newest is at the top, marked *Latest*).
3. Under **Assets**, download `arivna-browser-vX.Y.Z.apk` and `checksums.txt`.

## Verify the download (SHA-256)

Compute the file's SHA-256 and compare it with the value in `checksums.txt` and in the table above. They must match exactly; if not, delete the file and do not install it.

Windows (PowerShell):

```powershell
Get-FileHash .\arivna-browser-v1.0.1.apk -Algorithm SHA256
```

macOS:

```bash
shasum -a 256 arivna-browser-v1.0.1.apk
```

Linux:

```bash
sha256sum arivna-browser-v1.0.1.apk
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

## Signing certificate

Every official APK is signed with this certificate. Check it with `apksigner verify --print-certs arivna-browser-v1.0.1.apk`:

- Subject: `CN=Arivna Browser, O=Arivna, C=IN`
- SHA-256 fingerprint: `56:BE:21:31:F1:A1:B9:F5:AE:8A:2D:17:B0:2F:C4:14:89:A4:A4:4B:D1:69:BC:79:DB:74:A9:B3:29:F8:A5:AE`
