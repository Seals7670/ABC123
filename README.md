# Crate Player

A simple installable web app for playing your own audio files, with playlists, shuffle, repeat, and 15-second skip.

## Important: you must host this, you can't just open the file

iOS Safari will not install a PWA or run a service worker from a `file://` path. You need to serve these files over **HTTPS** first. Easiest free options:

1. **GitHub Pages** (recommended, free, permanent)
   - Create a new GitHub repo, upload all files in this folder (`index.html`, `manifest.json`, `sw.js`, `icons/`) to the repo root.
   - In the repo Settings → Pages, set the source to your main branch.
   - You'll get a URL like `https://yourname.github.io/reponame/`.

2. **Any static host** (Netlify, Vercel, Cloudflare Pages) — drag-and-drop this folder in.

## Installing on your iPhone 11

1. Open the hosted URL in **Safari** (must be Safari, not Chrome).
2. Tap the Share icon → **Add to Home Screen**.
3. Open it from the home screen icon — it now runs full-screen like a native app.

## Using it

- **Add songs**: tap "Add songs" and pick audio files from your Files app (or from "On My iPhone" / iCloud Drive downloads). Files are copied into the app's local storage (IndexedDB), so you only import each song once.
- **Playlists**: switch to the Playlists tab, create a playlist, then use the **⋯** menu next to any song to add/remove it from playlists.
- **Playback**: tap any song to play it and queue the rest of that list. Controls: shuffle, repeat (off/all/one), previous/next track, ±15s skip, and a scrub bar.
- **Search**: the search bar filters whichever list you're looking at (library or an open playlist).
- **Lock screen controls**: play/pause/skip/seek show up on the iPhone lock screen and Control Center while a track is loaded.

## Known iOS limitations (not bugs, just how Safari works)

- Safari can occasionally clear site storage if the app goes unused for a long time (Apple's storage eviction policy). If your library disappears after weeks of not opening it, you'll need to re-import songs.
- Background/lock-screen audio works while the app is open or backgrounded normally, but iOS may pause audio if the app is force-quit.
- There's no cloud sync — your library lives only on this device, in this browser.
