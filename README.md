# TrickRiders — Android

Unity Android game project (Unity 2022.3.62f1).

## Automatic APK build

The workflow is in `.github/workflows/android-apk.yml`. It runs manually from **Actions → Build TrickRiders Android APK → Run workflow**, and on pushes to `main` that change `Assets/`, `Packages/`, or `ProjectSettings/`.

Before the first build, configure these repository Actions secrets:

- `UNITY_LICENSE` — Unity license contents
- `UNITY_EMAIL` — Unity ID email
- `UNITY_PASSWORD` — Unity ID password

See the GameCI activation guide: https://game.ci/docs/github/activation

After a successful run, download the `TrickRiders-Android-APK` artifact. The APK is not available until a build succeeds.

## Project files

The repository must contain the Unity project folders `Assets/`, `Packages/`, and `ProjectSettings/` at its root. The CI build calls `AndroidGameBuilder.CreateGameSceneForCI` in `Assets/Scripts/Editor/AndroidGameBuilder.cs`.
