<div align="center">

<img src="Frontline/assets/banner.jpg" alt="FrontLine Lyrics" width="700"/>

**Real-time, synced lyrics for whatever is playing on your PC.**

</div>

---

> **⚠️ This is not the original project.** This is a personal fork/enhancement of **[FrontLine Lyrics Desktop](https://github.com/juliocax/FrontLine-Lyrics-Desktop)** by [@juliocax](https://github.com/juliocax) and contributors — all credit for the original application goes to them. This fork is **only available by cloning this repository and building it yourself** (it is not published on the Microsoft Store or anywhere else). For the original, unmodified project, go to **https://github.com/juliocax/FrontLine-Lyrics-Desktop**.

## Features (Original App)

- **Automatic track detection** via Windows Media Session (SMTC) — reads title, artist and playback position straight from any compatible player.
- **Audio-fingerprint recognition** as a fallback/primary source, using Shazam to identify what's playing from system audio.
- **Auto mode** that continuously re-listens and re-syncs as tracks change.
- **Pause-aware sync** — pausing the track pauses the lyrics too.
- **Live translation** into English, Spanish, French, Portuguese, or a romanized transliteration.
- **Manual search** for lyrics and cover art by artist/song name.
- **Playback shortcuts** (previous/next track) and manual sync-time adjustment, built into the overlay.
- **Adjustable font size** and a draggable, always-on-top, transparent overlay window.
- **Multi-language UI**: English, Portuguese, and Spanish.

## Features (This Enhancement)

- **Pin (click-through lock)**: right-click the tray icon and toggle **Pin** to lock the overlay in place — while pinned, mouse clicks pass straight through the whole window to whatever's behind it, so it never gets in the way or gets accidentally dragged, and it stops changing opacity on hover.
- **Adjustable lyric shadow**: a Settings slider controls how bold the dark outline behind the lyrics is, from none to very thick, with a solid black core so it stays dark even at maximum thickness.
- **Single-line lyric display**: shows only the current line instead of previous/current/next, for a cleaner look.
- **Lyric-matching fix**: cross-checks track duration when picking a lyrics match from LRCLIB, fixing cases where a same-artist, differently-titled song (e.g. "Stranger" vs "The Stranger") was shown instead of the real match.
- App icon embedded in the built `.exe` and its shortcut.

## Installation

This fork isn't packaged or published anywhere — build it from source:

1. Clone this repository:
   ```
   git clone https://github.com/kusnadin-ali/frontline-lyric-enhance.git
   ```
2. Install the [.NET 8 SDK](https://dotnet.microsoft.com/download) (`winget install Microsoft.DotNet.SDK.8` on Windows).
3. Build and run:
   ```
   dotnet build Frontline/Frontline.csproj
   Frontline\bin\Debug\net8.0-windows\Frontline.exe
   ```
   (Or open `Frontline.sln` in Visual Studio with the **.NET desktop development** workload installed, set `Frontline` as the startup project, and run it.)

The Python backend (`FrontlineServer`) is already bundled as a prebuilt `.exe` in the repo, so no Python setup is needed unless you're modifying that part of the code.

> **Windows Smart App Control**: if it's enabled in Enforce mode, it may silently block a freshly-built, unsigned `Frontline.exe`/`Frontline.dll` from launching (no error dialog — the process just exits). Either sign the build output with a locally-trusted certificate, or turn Smart App Control off in Windows Security (note: that's a one-way change, it can't be turned back on without reinstalling Windows).

## Usage Guide

1. Launch FrontLine Lyrics — the overlay appears on top of your other windows.
2. Play music in any app (Spotify, browser, local player, etc.).
3. Click **LISTEN** to start automatic recognition/follow, or toggle **AUTO** to keep it continuously syncing as tracks change.
4. Use **SEARCH** to look up lyrics by artist and song name directly.
5. Use the translation toggles (Orig / Rom / EN / ES / FR / PT) to switch how the lyrics are displayed.
6. Open **Settings** (⋮) to adjust font size, lyric shadow thickness, and background opacity; drag the window anywhere, and use the previous/next track buttons to control playback without leaving the overlay.
7. Right-click the tray icon and check **Pin** to lock the overlay click-through in place; uncheck it the same way to go back to normal.

---

Licensed under the MIT License (see [LICENSE.txt](LICENSE.txt)), same as the original project.
