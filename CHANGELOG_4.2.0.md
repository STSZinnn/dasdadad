# FrostPVP Reborn v4.2.0-beta1 — Team System & Config Redesign

## New persistent team system

Team data (team IDs, leader UUIDs, member UUIDs, names, colors, shared chest contents, named homes and numbered warps) is saved to `plugins/FrostPVP/teams.yml`. Existing weapon, event, trust and grace files are not replaced.

### Commands for team members

- `/frost team` — team command help
- `/frost team info` — team name, leader, member count, saved homes and warps
- `/frost team tpa <online teammate>` — request teleport; only same-team players accepted
- `/frost team tpaccept` / `/frost team tpdeny` — accept or decline a pending team request, expires after 60s
- `/frost team sethome <name>` — save/update named home (leader only)
- `/frost team home <name>` — teleport to a team home
- `/frost team setwarp <number>` — save/update a numbered warp (leader only)
- `/frost team warp <number>` — teleport to saved team warp (1-3 by default)
- `/frost team echest` — open the shared 54-slot team inventory

### Admin-only commands

- `/frost adminteam team create <name>` — create a new team; team names are 1-16 alphanumeric/underscore/hyphen characters (no spaces)
- `/frost adminteam team player <team> <player>` — assign an existing player; first assigned player becomes leader
- `/frost adminteam team rename <old> <new>`
- `/frost adminteam team echest see <team>`
- `/frost adminteam team color <team> <color>` — e.g. aqua, blue, red, green, gold, yellow, dark_purple
- `/frost adminteam team leader set <player>` — make a current team member leader
- `/frost adminteam team members <team>`
- `/frost adminteam team remove <player>` — remove a player
- `/frost adminteam team disband <team>` — permanently disband (back up teams.yml first)

### Display names

Team members receive color-coded player list names, chat display names, and overhead nametag color/prefix using Bukkit's main scoreboard teams. Other plugins that replace the main scoreboard or nametags may override this presentation.

### Reorganized /frost config

Five category pages: Weapons, Armor, Teams, Events, General. The Teams settings page allows operators to change whether named homes, warps, shared team chests and teleport requests are enabled, plus maximum homes and warps per team. Defaults: 3 warps, 3 homes, all four features enabled.

### Removed public commands

Removed `/frost cleartextures`, `/frost restyle`, and `/frost cooldowns` from command handling, help, and completions. Kept `/frost resetcooldowns` as an operator maintenance tool.

### Compatibility and safety

- Player/team IDs persist as UUIDs; renames do not reset membership.
- Shared chests are backed by a real shared 54-slot inventory and saved on close, quit and shutdown.
- Home and warp teleports use Paper's asynchronous teleport to avoid large synchronous chunk loads.
- Only operators (or holders of `frost.adminteam`) can create and manage teams.
- No changes to Frost weapons, PvP grace period, events or resource pack.
- This is a **source beta**. GitHub Actions compilation and live multiplayer testing remain necessary.
