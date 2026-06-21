---
title: "Managing Your Game Server"
description: "Understand the main server controls, files, backups, startup settings, users, schedules, and network allocations."
game: "minecraft-java"
category: "getting-started"
slug: "managing-your-game-server"
updated: "2026-06-21"
author: "WorldSpace Docs Team"
---

# Managing Your Game Server

The WorldSpace Game Panel brings the everyday server tools into one place. This guide explains what each area does and when to use it.

## Console and power controls

**Console** shows live server output and accepts server commands.

- **Start** launches a stopped server.
- **Restart** performs a controlled restart when the server responds normally.
- **Stop** requests a graceful shutdown so the game can save.
- **Kill** force-stops an unresponsive process. Use it only after a normal stop fails because unsaved data may be lost.

Do not include a leading slash when entering Minecraft commands in the panel console:

```text
say Server restart in 5 minutes
save-all flush
stop
```

## Resource usage

The dashboard displays CPU, memory, disk, and network activity. Brief CPU spikes during world generation are normal. Investigate when high usage is sustained and players experience delayed ticks or timeouts.

Disk usage includes worlds, logs, backups, plugins, mods, and archived files. Delete old logs and temporary archives only after confirming they are not needed.

## Files

Use **Files** for small uploads and configuration edits.

Common locations include:

| Path | Purpose |
|---|---|
| `/server.properties` | Core Minecraft settings |
| `/plugins` | Paper/Spigot-compatible plugins |
| `/mods` | Fabric, Forge, or NeoForge mods |
| `/world` | Main world, depending on `level-name` |
| `/logs/latest.log` | Most recent server log |
| `/config` | Mod and software configuration |

Stop the server before replacing worlds, server JARs, databases, or files that are written continuously.

## SFTP

Use SFTP for large worlds, modpacks, many files, or reliable downloads. Your connection details are shown in the server's **Settings** area. See [How to Connect with SFTP](./how-to-connect-with-sftp.md).

## Backups

**Backups** creates snapshots of server files. Before a risky change:

1. Stop the server or run `save-all flush`.
2. Create a backup with a descriptive name.
3. Wait until it is marked complete.
4. Download important backups to separate storage.

Restoring a backup replaces current files. Download anything created after the backup before restoring.

## Startup

**Startup** controls variables used to launch the server, such as:

- Minecraft version
- Server JAR filename
- Java runtime
- Loader or build number
- Additional startup arguments exposed by the server template

A wrong JAR name or Java version can prevent startup. Record old values before changing them.

## Network

**Network** lists the IP addresses and ports assigned to the server. The primary allocation is normally the address players use. Additional ports may be required for voice chat, query, maps, or proxy backends.

A plugin cannot use an arbitrary port unless that port is assigned to your server. Configure the plugin to use one of the listed allocations.

## Schedules

Use **Schedules** to automate safe, repeatable tasks such as announcements, saves, restarts, and backups.

A restart schedule should normally:

1. Warn players.
2. Run `save-all flush`.
3. Wait briefly.
4. Restart the server.

Avoid scheduling several heavy tasks—backup, restart, world trim, and mod update—at the same minute.

## Users

Use **Users** to give staff individual access. Assign only necessary permissions. For example, a developer may need files and console but not billing-related or user-management access.

## Databases

Some plugins use MySQL-compatible databases. Create a database in **Databases**, then copy its host, port, database name, username, and password into the plugin configuration.

Never use `localhost` unless the panel specifically shows it as the database host. Do not publish credentials in screenshots or public logs.

## Safe change routine

For any major change:

1. Announce downtime.
2. Save and stop.
3. Create a backup.
4. Change one thing at a time.
5. Start and read the console.
6. Test in game.
7. Document the working settings.

This routine makes troubleshooting faster and rollbacks much safer.
