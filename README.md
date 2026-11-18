# SAP2000 S2K Curtain Wall Generator — Android APK

This repository wraps the supplied standalone HTML application in Capacitor and builds an Android debug APK using GitHub Actions. Android Studio is not required on your computer.

## Build using GitHub (no Android Studio)

1. Create a **new GitHub repository**. A private repository is fine.
2. Upload the contents of this folder to the repository root. Keep the `.github/workflows/build-apk.yml` file and its folders; if hidden files are not shown by your file picker, enable showing hidden files or upload the workflow separately.
3. Use the default branch name `main`.
4. Open the repository's **Actions** tab. If prompted, enable GitHub Actions.
5. Select **Build Android APK** and click **Run workflow**. A push to `main` also starts a build automatically.
6. When the run completes successfully, open it and download the **S2K-CurtainWall-APK** artifact.
7. Extract the downloaded ZIP. Install `app-debug.apk` on your Android device. You may need to permit installation from your browser or file manager.

## App details

- App name: SAP2000 S2K Generator
- Android application ID: `com.engineeringtools.s2kcurtainwall`
- Web entry point: `www/index.html`
- Capacitor: 8.0.0

## Updating the HTML application

Replace `www/index.html` with the updated HTML file and commit/push the change to `main`. GitHub Actions will build a fresh APK.

## Notes

- The generated APK is a **debug APK** for testing and direct installation. It is not a signed Play Store release.
- The application is self-contained and currently has no external CSS, JavaScript, font, or image URL dependencies.
- The HTML generator creates `.s2k` text for import into SAP2000; this Android wrapper does not include SAP2000 itself.
- If you change the Android application ID or app name, update `capacitor.config.json` before the next build.
