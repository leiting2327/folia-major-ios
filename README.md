# folia-major-ios

Build [Folia](https://github.com/chthollyphile/folia-major) (lyrics reimagined, MIT) into an **iOS IPA** using [Capacitor](https://capacitorjs.com), driven by GitHub Actions on a macOS runner (Xcode).

## What this does

1. Clones the upstream `chthollyphile/folia-major` source.
2. Builds its web bundle (`npm run build` → `dist/`).
3. Wraps it in a Capacitor iOS project.
4. `xcodebuild`s an **unsigned** `Folia.ipa` (no signing certificate needed).
5. Uploads the IPA as a workflow artifact `Folia-ipa`.

## How to get the IPA

- Open the **Actions** tab → pick the latest **Build iOS IPA** run → download the **Folia-ipa** artifact.
- The produced `Folia.ipa` is unsigned. To install on a real iPhone, re-sign it with your own Apple ID via **Sideloadly** or **AltStore** (free, no paid developer account required).

## Notes

- Deployment target is iOS 15.0+ (covers iPhone 6s / 6s Plus and newer).
- `cleartext` is enabled so HTTP endpoints used by the music backends are not blocked by ATS.
- To trigger manually: **Actions → Build iOS IPA → Run workflow**.
