# Releasing (maintainer notes)

## Version naming
- Tag and release name: `vMAJOR.MINOR.PATCH` (e.g. `v1.0.1`), matching `versionName` in `app/build.gradle.kts` of the source repo.
- `versionCode` must go up by at least 1 on every release (Play rejects equal or lower, and Android will not install a lower one over a higher one). Never reuse a versionCode.
- Patch: fixes only. Minor: new features. Major: big or breaking changes (e.g. raised minSdk).

## File naming
- APK: `arivna-browser-v1.0.0.apk`
- Checksums: `checksums.txt`, one line per file in `sha256sum` format:
  ```
  <64 hex chars>  arivna-browser-v1.0.0.apk
  ```

## Steps
1. In the source repo: bump `versionCode` / `versionName`, update `CHANGELOG.md`, commit, tag `vX.Y.Z`.
2. Build the bundle: `./gradlew bundleRelease` and upload it to Play Console.
3. Get the APK: once Play App Signing is active, download the **signed, universal APK** for that version from Play Console (App bundle explorer > Downloads). Do not publish an APK signed locally with the upload or debug key: the README promises the APK has the same signature as the Play version.
4. Rename it to `arivna-browser-vX.Y.Z.apk` and create the checksum:
   ```bash
   sha256sum arivna-browser-vX.Y.Z.apk > checksums.txt
   ```
   (Windows: `(Get-FileHash .\arivna-browser-vX.Y.Z.apk -Algorithm SHA256).Hash.ToLower() + "  arivna-browser-vX.Y.Z.apk" | Out-File -Encoding ascii checksums.txt`)
5. Check the signature: `apksigner verify --print-certs arivna-browser-vX.Y.Z.apk` (from Android SDK build-tools) and compare the SHA-256 certificate digest with Play Console > App integrity > App signing key certificate.
6. Create the GitHub Release in this repo:
   ```bash
   gh release create vX.Y.Z arivna-browser-vX.Y.Z.apk checksums.txt \
     --repo viroaryan/arivna-browser-releases --title "Arivna Browser vX.Y.Z" \
     --notes "Changes: https://github.com/viroaryan/arivna-browser/blob/HEAD/CHANGELOG.md"
   ```
   Or on github.com: Releases > Draft a new release > tag `vX.Y.Z` > attach both files > Publish.
7. Add a row to the Versions table in `README.md` with the date, minSdk, release link and the SHA-256 (replace `TBD`), and commit.
8. Update the website's download page and changelog.

Never delete or replace the files of a published release; publish a new version instead.
