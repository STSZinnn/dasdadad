# Frost Music system: Paper 1.21.11

## Automatic behavior
- Ominous Trial Spawner becomes ACTIVE / WAITING_FOR_REWARD_EJECTION: anyone within 32 blocks hears Breeze.
- Wither within 64 blocks (approximate boss bar listening range): player hears Conviction.
- One per-player music stream at once. Multiple spawners never stack sound events.
- Changes and stops take up to 2 seconds to detect. Wither has priority.
- Uses the Jukebox/Note Blocks sound category.
- When each full song starts (and when it loops), the plugin sends the exact Now playing chat credit.

## Required for the full music tracks
The provided resource-pack ZIP contains short original test tones. The actual third-party songs are not included.
Install authorized copies of BOTH audio recordings locally:

`python3 install_authorized_music.py --pack Frost_Sovereign_EndReborn_Music_Template_1.21.11.zip --breeze /path/to/Breeze.mp3 --conviction /path/to/Conviction.mp3 --output My_Server_Music.zip`

Requires Python 3 and `ffmpeg` on PATH. Output is a Minecraft resource-pack ZIP suitable for 1.21.11.
This command reads the audio files on your machine and does not upload them anywhere.
Enable the *generated* pack in Options -> Resource Packs. Remove the template pack after installation.

## Testing
`/frost config` -> General -> Boss and Trial Soundtracks: enable/disable and adjust detection radius.
Start an ominous trial near an active ominous spawner and enter its radius; spawn a Wither (in a test world) and move within 64 blocks. Music should stop outside the configured range.

## Limitations
- The Wither audio is scoped by distance (64 blocks by default), matching typical boss bar range; it does not inspect the network's per-player boss-bar visibility state.
- A client needs the resource pack for sound events to be audible.
- The custom sound events cannot auto-replace other datapacks' separately managed music; test alongside End Reborn if both music systems could be active simultaneously.
- Full Paper compilation/gameplay testing is not yet confirmed.
