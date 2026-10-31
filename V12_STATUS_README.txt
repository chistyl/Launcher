CleanYourTV V12 source project

This is the CleanYourTV source project supplied by the user, updated with the V12
changes described in V12_CHANGELOG.md.

The V12 source changes include:
- Rounded A+ launcher icon assets and adaptive icon manifest configuration.
- Desktop visibility filtering that also hides apps inside system and regular folders.
- Wider desktop visibility and folder dialogs.
- Spaced folder-name input field.
- Square folder app tiles with consistent focus proportions.
- Add-app (+) tile in both regular and system folders.
- Per-app custom background colour carried through to bannerless desktop tiles,
  folder contents and folder preview thumbnails, with a default background fallback.

Build status: source updated; APK not built. The build environment has no Android SDK
and cannot download Gradle 8.9 from services.gradle.org. See V12_CHANGELOG.md.

\nAdditional folder long-press parity update:\n- Folder app long-press now exposes the same app customization actions as desktop tiles, plus a folder-specific move-out action.\n- Folder tiles now use the desktop default white background for bannerless apps, preserve custom background/icon/size settings, and use square synchronized focus scaling.\n- Folder and visibility dialogs widened to a maximum of 760dp.\n\nValidation: 110 Android XML files parse successfully; Java delimiter structure checks pass. APK build has not been run because Android SDK/Gradle are unavailable in this container.\n