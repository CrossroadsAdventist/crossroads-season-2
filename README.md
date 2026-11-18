# Crossroads — Season 2 player (GitHub Pages)

A shareable web player for the Season 2 episodes of Crossroads so far.
The page and the audio live together in this folder, so the player works
from any device or Google account — no Spotify needed. This is the
no-Spotify route for Hanna's mom, who doesn't use Spotify.

## What's in this folder

- `index.html` — the player page (episode list, Play All, seek, back-to-back
  auto-advance, remembers where you stopped). Adapted from the tested
  Season 1 player; JS syntax checked.
- `episode-22-everybody-was-invited-mini-movie.mp3` — Episode 22,
  "Everybody Was Invited (Mini Movie)", 41:40, 60,003,727 bytes,
  md5 ba822e044d9b4cd5837a93d62c5e68b5 (the fixed v2 master).
- `episode-23-the-thing-in-the-dark.mp3` — Episode 23, "The Thing in the
  Dark", 35:07, 50,572,315 bytes, md5 c4d7d911de884d041c66cb423696930b
  (the fixed v2 master, Ethan re-voiced).
- Total ~106 MB; each file is under GitHub's 100 MB per-file limit.
- `cover.jpg` — the show cover art (800 px).

## How to publish it (GitHub Pages)

Same method as Season 1 (GitHub account: CrossroadsAdventist, repo per
season, deploy key 'Poppy' with write access, gh CLI). Do NOT publish
until Hanna says yes — this folder is prepared, not live.

1. Create the public repo `crossroads-season-2` on the CrossroadsAdventist
   account.
2. Copy everything from this folder into it, commit and push.
3. On github.com, open the repo → Settings → Pages → under "Branch"
   choose `main` and `/ (root)`, then Save.
4. Expected live URL (same pattern as Season 1):
   `https://crossroadsadventist.github.io/crossroads-season-2/`
5. Test before sharing: Episode 22 plays, seeking works, Episode 22
   auto-advances to Episode 23, and the page opens on a phone with no
   sign-in — the same checks that passed for Season 1.

## Continuous mode (Keep playing with screen off)

The player has a "Keep playing with screen off" button. It plays the
~2-hour chunk recordings from the
[`crossroads-continuous`](https://github.com/CrossroadsAdventist/crossroads-continuous)
repo instead of the individual episode files, so playback keeps going
when a phone screen turns off (a frozen page can't run the per-episode
auto-advance). The lock screen still shows the episode that's playing.
Season 2's chunk lives in that repo; this page polls its `chunks.json`
every 5 minutes and picks up rebuilt chunks without a refresh.
**This file is the template for the combined All-Episodes player** —
`player-deploy-all/build_combined.py` builds that page from this one,
so keep the chunk code here in sync with the combined page.

## Updating it later

To add a future Season 2 episode, drop the new MP3 into the repo folder,
add its entry to the EPISODES list in `index.html` (episode numbers run
continuously across seasons: Season 2 starts at 22), commit and push.
Then rebuild the Season 2 continuous chunk (see the rebuild rule in the
`crossroads-continuous` repo README — only the last chunk is rebuilt,
append-only) and re-run `build_combined.py` for the All-Episodes page.

## Other places to listen

- Spotify: https://open.spotify.com/show/4kSRaNLoz4u34nFCMUw7KV
  (Episode 22: https://open.spotify.com/episode/3Znci0ZZch2y0RZVFlzYkt ;
   Episode 23: https://open.spotify.com/episode/1MpXftFEcpf89dSxtRF0bI)
- Google Drive folder (full-quality files):
  https://drive.google.com/drive/folders/1ycbZTgMK3zHMKOeKOfqJWGrsqoL8gJnZ
- Season 1 player (Episodes 1–21):
  https://crossroadsadventist.github.io/crossroads-season-1/
