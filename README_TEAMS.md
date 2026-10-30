# Frost Teams — Quick Start

Use the same FrostPVP jar; no separate plugin required. Server owners should back up `plugins/FrostPVP` before installing. Team data is written to `plugins/FrostPVP/teams.yml` when teams are created.

As operator:

    /frost adminteam team create Aurora
    /frost adminteam team player Aurora PlayerOne
    /frost adminteam team player Aurora PlayerTwo
    /frost adminteam team color Aurora aqua
    /frost adminteam team leader set PlayerOne
    /frost adminteam team members Aurora

As **team leader**:

    /frost team sethome base
    /frost team setwarp 1
    /frost team setwarp 2
    /frost team setwarp 3

As any member:

    /frost team home base
    /frost team warp 1
    /frost team echest
    /frost team tpa PlayerTwo

The receiving teammate can type `/frost team tpaccept` or `/frost team tpdeny` within 60 seconds.

## Teams config

All settings are available at `/frost config` → Teams → Team Settings.

    teams:
      homes-enabled: true
      max-homes: 3
      warps-enabled: true
      max-warps: 3
      echests-enabled: true
      tpa-enabled: true

## Notes

The first player assigned to a new team becomes its leader automatically. Only admins can assign members; members cannot create teams. Team colors use the built-in Minecraft chat colors. Team displays use the server's main scoreboard; other scoreboard/nametag plugins can override them. Persistent team inventory is shared, not a separate copy per member. The last update came from FrostPVP Reborn v4.1.3-beta1; this build is v4.2.0-beta1 source and requires GitHub Actions to compile.
