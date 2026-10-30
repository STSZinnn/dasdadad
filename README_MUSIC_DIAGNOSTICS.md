# FrostPVP v4.3.1 Music Diagnostics — Paper 1.21.11

The ZIP contains source, not a compiled JAR. Build with `.github/workflows/build.yml` on GitHub Actions.
The new workflow captures `frost-build.log` and uploads it even if compilation fails.

**IMPORTANT:** The supplied combined resource pack only contains SHORT ORIGINAL TEST TONES.
It does not contain the uploaded artists' full songs. If you have permission to use copies
of the songs, use the previously provided local authorized-audio setup script.

## Diagnose a silent track

1. Ensure the plugin **JAR**, not source ZIP, is inside `plugins/` and `/plugins` lists FrostPVP.
2. In Minecraft, enable the combined Frost+Sovereign+EndReborn music resource pack and reload using F3+T.
3. Set Options -> Music & Sounds -> Jukebox/Note Blocks volume above 0 and Master Volume above 0.
4. Test: `/frost music test breeze` or `/frost music test conviction` (OP required).
   These play the known original test tone and DO NOT require a nearby Wither/trial.
5. Stop tests with `/frost music stop`.
6. `/frost music status` shows whether the Wither or ominous trial is detected and which track is selected.
7. If a test is silent despite the pack being enabled, look in `latest.log` for missing sound event/resource warnings.

Music now uses Adventure audience playback instead of emitting a sound at a stationary location.
The Wither must be alive within 64 blocks, and an ominous Trial Spawner must be ominous and ACTIVE
(or WAITING_FOR_REWARD_EJECTION) within 32 blocks. Changing settings with `/frost reload`
is supported.

The Ender Dragon song still requires the separate End Reborn music controller datapack; it is NOT
triggered by FrostPVP. Its sound event stays bundled in the combined resource pack.

## Fix build failure

Open GitHub -> Actions -> latest red workflow -> Build plugin and capture errors.
Look for the first `error:` in Java source or `Could not resolve` dependency errors.
Download artifact `FrostPVP-v4.3.1-build-log` and send the full log.
A local syntax-only check cannot prove compatibility with Paper 1.21.11.
