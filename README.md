# XcodeBuildDemo

A minimal SwiftUI iOS app that builds with `xcodebuild` and uploads to AutoDevice via GitHub Actions.

## Local Build

```bash
xcodebuild build \
  -project XcodeBuildDemo.xcodeproj \
  -scheme XcodeBuildDemo \
  -sdk iphonesimulator \
  -configuration Debug \
  -derivedDataPath build \
  CODE_SIGN_IDENTITY="" \
  CODE_SIGNING_ALLOWED=NO
```

The `.app` bundle will be produced under `build/Build/Products/Debug-iphonesimulator/`.

## CI/CD

The GitHub Actions workflow (`.github/workflows/build.yml`) builds the app for the iOS simulator and uploads the resulting `.app` to AutoDevice.

### Required Secrets

- `AUTODEVICE_API_KEY` — your AutoDevice API key for uploading builds

