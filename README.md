# Vinyl Room

A turntable skin for Spotify. One file: `index.html`.

**Live:** https://jp-27.github.io/vinyl-room/
Spotify redirect URI for the live page: `https://jp-27.github.io/vinyl-room/`

## Run it

Spotify sign-in needs a real local address, so serve the folder instead of double-clicking the file:

```
cd vinyl-room
python3 -m http.server 8888 --bind 127.0.0.1
```

Open http://127.0.0.1:8888 (use `127.0.0.1`, not `localhost`; Spotify rejects `localhost` redirects).
Without connecting, it runs in preview mode with four sample records.

## Connect Spotify

1. Go to https://developer.spotify.com/dashboard and create an app. Tick **Web API** and **Web Playback SDK**.
2. Add the redirect URI `http://127.0.0.1:8888/` (the menu shows the exact one to copy).
3. Under **User Management**, add the Spotify account you'll sign in with (apps start in development mode).
4. In Vinyl Room, open the menu, paste the Client ID, press **Connect Spotify**.

## What you get

- **Premium:** the page becomes a Spotify device called "Vinyl Room" and plays in the browser.
- **Free:** the page follows whatever Spotify is playing on your phone or desktop app (cover, vinyl, lyrics, track rail all update). Spotify only allows Premium accounts to start or skip playback from other apps.
- Lyrics come from LRCLIB (free, no key). Not every track has synced lyrics.
- "React to room sound" in the menu uses the mic so the glow pulses with the music. Spotify no longer gives new apps per-song beat data, and its in-browser audio is DRM-protected, so the mic is the only way to get a real signal.

## Host it online (optional)

Put `index.html` on any HTTPS host (GitHub Pages, Netlify, Vercel), add that page's URL as a second redirect URI in the Spotify dashboard, and connect from there.
