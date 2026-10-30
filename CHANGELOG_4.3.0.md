# FrostPVP Reborn v4.3.0 (Paper 1.21.11) — Soundtrack and Eclipse Dance

- Added `FrostMusicManager.java`, a per-player, main-thread music controller with a 40-tick scan.
- When an ominous Trial Spawner is actively spawning or waiting to eject a reward within 32 blocks of a player, play the custom sound event `frostmusic:breeze`.
- When an alive Wither is within 64 blocks, play `frostmusic:conviction`, with priority over the trial soundtrack.
- Only one music event plays per player at once, regardless of how many trial spawners are active.
- Tracks resume/loop once their configured duration elapses (Breeze 121.652 sec, Conviction 343.771 sec), not whenever another spawner activates.
- Music stops on exit/combat end, player quit, plugin shutdown, or switches when appropriate.
- Tracks are on the RECORDS sound channel (Jukebox/Note Blocks slider).
- Announces once per playback start: `Now playing: [Breeze] by TenM` or `Now playing: [Conviction] by FPLester`.
- Eclipse Dance now triggers by RIGHT-CLICK while Dayblade and Nightblade are equipped, one in mainhand and one offhand; the F key becomes ordinary offhand swap.
- Updated Eclipse Dance action bar, custom item descriptions, and configuration settings.
- Existing Frost Teams, armor, grace, events, combat abilities and persisted settings retained.

## Important
- The combined pack includes original short TEST sounds rather than third-party music recordings.
- To hear the full tracks, generate a personal-use resource pack by running the included installer with properly licensed audio files. Do not re-distribute artists' music without permission.
- Code structure, JSON, archive and local Java syntax checks completed; full Paper compilation and live trials remain unverified.
