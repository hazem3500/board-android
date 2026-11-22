# oz-home Board for Android

Signed APK builds of the oz-home Board app, published here so [Obtainium](https://obtainium.imranr.dev/) can install and update it.
This repository holds releases only: no source and no secrets. The app is a Trusted Web Activity for
`https://board.zem.cool/oz/`, which stays behind Cloudflare Access.

Add it in Obtainium: [obtainium://add/https://github.com/hazem3500/board-android](https://apps.obtainium.imranr.dev/redirect?r=obtainium://add/https://github.com/hazem3500/board-android)

Release signing certificate (SHA-256), the same one `https://board.zem.cool/.well-known/assetlinks.json` lists:

```
A5:09:B0:69:00:08:F9:DA:B6:FA:3B:90:90:D0:67:A6:BF:B6:BA:11:2B:41:AB:AE:F4:54:D3:32:50:2F:9A:F3
```

Releases are pushed by the private build as a tag `vX.Y.Z` whose commit holds `board.apk` and `NOTES.md`;
`.github/workflows/release.yml` checks the APK's signer against the fingerprint above and publishes the release.
