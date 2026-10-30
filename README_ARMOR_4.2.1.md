# FrostPVP Reborn v4.2.1 — Armor and Fishing Rod update

- Powder snow becomes temporary solid snow beneath Frozen Boots (1-second restored trail; remains solid if continuously refreshed). Restoration occurs when the block expires, chunks unload, or the plugin disables. Only powder-snow blocks are modified.
- Frozen Helmet reveals eligible nearby enemy players after five continuous seconds of crouching; sends authentic sculk vibration particles from detected players to helmet wearer every 30 ticks during the 10-second reveal.
- Armor HUD displayed as a compact vanilla subtitle, separate from the weapon action bar: Helmet detection and full-set Winter's Awakening cooldowns (including charging/ready states). Because vanilla Minecraft doesn't have an extra low-HUD text slot, the subtitle is located above the action bar and can overlap other plugins' title/subtitle announcements.
- Leggings grant fall damage immunity, retain Fire Resistance.
- Frozen Boots retain Speed II and 10% snow movement bonus, with +0.20 water_movement_efficiency attribute bonus (the precise resulting velocity depends on Minecraft's movement and enchantment modifiers).
- Helmet Respiration V; all four items Protection IV. Existing equipped authentic armor items are updated automatically once per second without replacing the item.
- Frozen Fishing Rod retired: removed from menu, items no longer recognized for Frost abilities, no config page, no cooldown; existing old rods remain vanilla fishing rods with previously stored item metadata.
- All previously implemented Frost teams, weapons, events, grace periods, and source assets are retained.
- Safety: temporary snow blocks are capped at 192 per server, cannot be mined/placed over, and restored on disable or chunk unload. Crash recovery is not guaranteed. Keep world backups.
- This is a test source release. Full Paper compilation/live tests have not been completed.
