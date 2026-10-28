# Royal Games Admin APK

Admin panel for Royal Games, as an Android app. The admin page itself is
bundled in `www/index.html` (no remote URL); it talks to the Royal Games
Firebase Realtime Database over the internet, so the phone needs internet
when using it.

## Push flow (GitHub Codespace, same route as the game app)

1. Create a new PUBLIC GitHub repo (for example `royal-games-admin-app`),
   open its Codespace.
2. Upload this ZIP into the Codespace and run:

```
unzip -o royal-games-admin-apk.zip
cp -r royal-games-admin/. .
git add www capacitor.config.json package.json .github/workflows/build.yml .gitignore README.md
git commit -m "Royal Games Admin APK"
git push
```

3. GitHub Actions builds the APK (branch: main).

## Download

Actions -> latest run -> Artifacts -> `royal-games-admin-apk`.
Uninstall any older admin APK first (each build signs with a fresh debug
key), then install `app-debug.apk`.

## WARNING — keep this APK private

This app talks to a database that is currently in Firebase test mode
(open read/write). Anyone with this APK can reach the admin data. NEVER
share the APK publicly, never post its download link anywhere public.
First open asks you to set a 4-digit PIN; keep that PIN private too.
