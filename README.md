# oz-home Board for Android: releases-only mirror

This repository is a releases-only mirror. The app's source and its release build live in the private Board monorepo
(`apps/android`, Wear module included); an `android-vX.Y.Z` tag there builds, signs and pushes the release here.
Nothing changes for Obtainium: same repository, same package, same signing key, same APK names.

Signed APK builds of the oz-home Board app, published here so [Obtainium](https://obtainium.imranr.dev/) can install and update it.
This repository holds releases only: no source and no secrets. The app is a Trusted Web Activity for
`https://board.zem.cool/oz/`, which stays behind Cloudflare Access.

Add it in Obtainium: [obtainium://add/https://github.com/hazem3500/board-android](https://apps.obtainium.imranr.dev/redirect?r=obtainium://add/https://github.com/hazem3500/board-android)

Release signing certificate (SHA-256), the same one `https://board.zem.cool/.well-known/assetlinks.json` lists:

```
A0:07:FB:AA:AA:E0:BF:BF:EA:93:CB:82:98:E4:D4:FD:8C:55:C2:D4:BB:E9:B6:BD:B0:1B:8E:F6:0D:7D:DC:57
```

Releases are pushed by the private monorepo's CI as a tag `vX.Y.Z` whose commit holds `board.apk` and `NOTES.md`;
`.github/workflows/release.yml` checks the APK's signer against the fingerprint above and publishes the release.

From v1.4.0 a release also carries the Pixel Watch app, `oz-home-board-wear-vX.Y.Z.apk`, signed with the same key.
Install it on the watch with Wear Installer or `adb`, then pair from the watch. In Obtainium, set the Board app's
"Filter APKs by regular expression" to `^oz-home-board-v` so the phone keeps updating the phone APK without asking.
