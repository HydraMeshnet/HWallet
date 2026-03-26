# Security

## Verifying Official Releases

Every APK is cryptographically signed. Before installing, confirm the signing certificate matches these fingerprints:

| Algorithm | Fingerprint |
|-----------|-------------|
| SHA-256 | `66443797e7ec86585f74386538e6e21d3058b639e8dd87dc48ca48374df2123b` |
| SHA-1 | `c821f27f58f2e29ac3c5a0209ded9006cb49807f` |
| MD5 | `cb7d5c1064f15999b2ebef4ca6a2a6a1` |

### How to Verify

**Certificate check** (requires Android SDK):

```bash
apksigner verify --print-certs xxx.apk
```

Match the SHA-256 digest from the output against the table above.

**Integrity check** (using the `.sha256` file bundled with each release):

```bash
sha256sum -c xxx.apk.sha256
```

### Verification Failure

If either check fails, do not proceed with installation. Remove the APK immediately and obtain a fresh copy exclusively from the official GitHub Releases page or our official FDroid repo. If you believe the APK has been tampered with, inform us via email at info@hydramesh.net.

Android enforces signature consistency across updates automatically, so once your first install is verified, future updates are protected by the OS.
