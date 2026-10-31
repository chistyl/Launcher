# V12 Step Next — folder app long-press parity

Base: the closest complete CleanYourTV V12 source archive, preserving its A+ adaptive launcher icon and prior V12 changes.

This iteration updates:
- `MainActivity.java`: folder app long-press opens the desktop-style customization menu (rename, global app-name visibility, custom icon, icon size, background color, reset app customizations, remove shortcut when enabled, app info) plus the folder-specific move-out action.
- Folder edits reopen the folder after app customization, including icon-picker return/cancel.
- Folder app tiles honor custom icon and explicit icon-size settings.
- Bannerless folder app tiles use the same default white background as desktop bannerless tiles, while preserving the saved per-app background.
- Folder dialog max width and desktop visibility dialog max width are 760dp; folder app tiles and the add tile use the same X/Y focus scale and remain square.
- Folder dialog uses rounded outer surface and consistent tile margins.

Validation performed:
- 110 Android XML files parsed successfully.
- MainActivity.java and AppAdapter.java delimiter structure checks passed.
- `javac` reported no Java grammar/syntax diagnostics; full compilation is unavailable because Android SDK and Gradle are not installed in this container.

Build status:
- Source package only. No APK has been built or device-tested.
- Build using the repository's `.github/workflows/android-build.yml` workflow or Android Studio with JDK 17 and Android SDK 34.
