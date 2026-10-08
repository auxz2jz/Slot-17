# 3D Scan Studio — Isolated APK Builder

This repository (Slot-17) is **a build-only workspace** for the unchanged **Slot-8 / 3D Scan Studio Android v0.26.0** source package.

**Slot-8 is not modified.** No project logic is altered by this workflow. An APK build is not a guarantee that all device features work.

## One-time source upload

This builder expects the **original unmodified ZIP** at:

`source/PhotogrammetryStudioAndroid-v0.26.0-Distortion-Aware-Laser-3D-Android-Studio-Ready.zip`

Expected SHA-256:

`8a9155a10424dc6c255141c8a46ead78b826ba3bb566e639e33be9f5d4b5ea7e`

Download that exact ZIP from the ChatGPT project archive, then:

1. Open the [source folder](https://github.com/auxz2jz/Slot-17/tree/main/source).
2. Click **Add file → Upload files**, or navigate to the folder and use the plus/menu upload option.
3. Upload the original ZIP **without extracting or renaming it**.
4. Commit the upload to `main`.

The push automatically triggers [Build 3D Scan Studio Android APK](https://github.com/auxz2jz/Slot-17/actions/workflows/build-apk.yml). You can also launch it with **Run workflow** under the Actions tab after upload.

## Retrieve the APK

Open the most recent successful workflow run and download the artifact named:

`3D-Scan-Studio-v0.26.0-debug-apk`

Extract that artifact ZIP to get `app-debug.apk`, installable on a compatible Android phone (subject to Android app install permissions).

The job is configured to use:
- GitHub-hosted Ubuntu runner;
- Java 17;
- Android SDK platform 37 and build-tools 36.0.0;
- unchanged project's embedded Gradle 9.6.0 wrapper;
- `./gradlew --no-daemon --stacktrace :app:assembleDebug`;
- an exact source-archive SHA-256 verification before building.

If dependencies or compilation fail, read the job log. No APK is uploaded unless the build produces one. This repo is public, so avoid uploading secrets or signing keys.
