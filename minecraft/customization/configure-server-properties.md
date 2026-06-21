---
title: "How to Configure Your Server Properties"
description: "Edit common Minecraft: Java Edition settings in server.properties safely."
game: "minecraft-java"
category: "customization"
slug: "configure-server-properties"
updated: "2026-06-21"
author: "WorldSpace Docs Team"
---

# How to Configure Your Server Properties

`server.properties` contains core Minecraft server settings. The file is created after the first successful launch and is read when the server starts.

## Edit the file safely

1. Stop the server.
2. Open **Files → server.properties**.
3. Change only the value after `=`.
4. Keep one setting per line.
5. Save the file and start the server.
6. Check **Console** for invalid-value warnings.

Do not add spaces around the `=` unless the value itself intentionally contains them.

## Common settings

| Setting | Example | Purpose |
|---|---|---|
| `motd` | `A WorldSpace Server` | Multiplayer-list description |
| `gamemode` | `survival` | Default mode for new players |
| `difficulty` | `normal` | peaceful, easy, normal, or hard |
| `max-players` | `20` | Displayed connection limit |
| `pvp` | `true` | Enables player-versus-player damage |
| `online-mode` | `true` | Verifies Java player accounts |
| `white-list` | `false` | Restricts access to allowed players |
| `enforce-whitelist` | `true` | Removes non-allowed online players when enabled |
| `allow-flight` | `false` | Prevents flight-kick checks from blocking legitimate flight |
| `enable-command-block` | `false` | Enables command blocks |
| `spawn-protection` | `16` | Protects blocks near world spawn from non-operators |
| `view-distance` | `10` | Maximum chunks sent around each player |
| `simulation-distance` | `10` | Radius where entities and game logic tick |
| `level-name` | `world` | Folder name of the active world |
| `level-seed` | *(blank)* | Seed used when generating a new world |
| `generate-structures` | `true` | Generates villages and other structures in new chunks |
| `hardcore` | `false` | Enables hardcore rules for the world |

## Important notes

### `server-ip`

Leave this blank unless WorldSpace support specifically instructs otherwise:

```properties
server-ip=
```

Binding to an unassigned address can prevent the server from starting.

### `server-port`

Use the primary port assigned in **Network**. Changing it to an unassigned port can make the server unreachable.

### `level-name`

This must match the exact world folder name. Changing it does not rename or move the existing world; it tells the server to load another folder or create a new one.

### `level-seed`

The seed affects newly generated worlds or chunks. Changing it after a world exists does not regenerate existing terrain and can create sharp borders between old and new chunks.

### View and simulation distance

Higher values increase CPU, memory, and network usage. Increase gradually and measure tick performance. Software-specific configuration may impose another limit.

### Online mode

Keep `online-mode=true` on a normal standalone server. Proxy networks require a deliberate authentication and forwarding design; do not disable it without completing that setup.

## Example balanced configuration

```properties
gamemode=survival
difficulty=normal
max-players=20
pvp=true
online-mode=true
white-list=false
allow-flight=false
enable-command-block=false
spawn-protection=16
view-distance=10
simulation-distance=8
level-name=world
```

## The file resets or changes values

Possible causes include:

- The server was running while you edited it and rewrote the file on shutdown.
- A startup variable manages the same setting.
- A plugin or mod controls the value elsewhere.
- The value is unsupported and the server restored a default.

Stop the server before editing and read the startup log for warnings.
