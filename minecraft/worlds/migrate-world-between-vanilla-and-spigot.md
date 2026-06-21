---
title: "Migrating Your World Between Vanilla and Spigot-Based Software"
description: "Move a world between Vanilla and Bukkit-derived servers while accounting for version-specific dimension layouts."
game: "minecraft-java"
category: "worlds"
slug: "migrate-world-between-vanilla-and-spigot"
updated: "2026-06-21"
author: "WorldSpace Docs Team"
---

# Migrating Your World Between Vanilla and Spigot-Based Software

Vanilla, Spigot, Paper, and their forks may store dimensions or world metadata differently depending on the Minecraft and server-software generation. Modern releases have changed some of these layouts, so do not follow an old folder-moving guide without checking your exact version.

> **Create a full backup and test the migration on a copy.** A successful startup does not prove that Nether, End, entities, or plugin data migrated correctly.

## Before you begin

Record:

- Current Minecraft version
- Current server software and build
- Target software and build
- `level-name` from `server.properties`
- Existing world-related folders
- Whether mods added blocks, entities, dimensions, or world-generation data

Stop the server and download a full backup.

## Vanilla to Paper or another compatible fork

For a supported modern Paper migration, the safest path is usually:

1. Stop the Vanilla server.
2. Back up all files.
3. Replace the server JAR with the target Paper-compatible JAR.
4. Keep the same `level-name`.
5. Start the server once and let the software perform its supported conversion.
6. Check every dimension and important location.

Do not manually split dimension folders unless the target software's current documentation specifically requires it.

## Spigot/CraftBukkit to modern Paper

Direct migration behavior can differ by generation. For current software, consult the target project's migration notes before moving folders. A version bridge through Vanilla may be required for some combinations.

Use a test server and compare:

- Overworld, Nether, and End spawn points
- `level.dat` and player data
- Portal destinations
- Plugin-created worlds
- World-management plugin configuration

## Returning to Vanilla

Older Bukkit-derived layouts commonly used:

```text
/world
/world_nether/DIM-1
/world_the_end/DIM1
```

while older Vanilla layouts commonly used:

```text
/world
/world/DIM-1
/world/DIM1
```

However, newer server generations may store dimensions and world metadata differently. Use the migration instructions for the exact source build. Blindly moving only `DIM-1` and `DIM1` can omit newer metadata files.

A safe return process is:

1. Stop and back up.
2. Read the source software's current migration guide.
3. Move or convert all listed dimension and metadata files on a copy.
4. Replace the JAR with the exact matching Vanilla version.
5. Start in a test server.
6. Check dimensions, advancements, raids, maps, portals, and scheduled events.

## Modded worlds

Vanilla or plugin-only software cannot safely represent blocks, items, entities, biomes, or dimensions added by mods. Removing the loader may delete or replace modded content.

Do not migrate a modded world to Vanilla/Paper unless:

- All content mods have documented removal procedures.
- Players remove modded items from inventories and containers.
- You have tested a copy thoroughly.
- You accept that some data may be unrecoverable outside the backup.

## Plugin-created worlds

World-management plugins may use custom folder names or environment settings. Copy those folders and plugin configuration together. Vanilla loads only the world selected by `level-name` and does not automatically load every extra world folder.

## Verification checklist

- [ ] Correct overworld spawn and seed
- [ ] Nether builds and portals present
- [ ] End builds, dragon state, and gateways present
- [ ] Player inventories, advancements, and statistics present
- [ ] Villagers, entities, and item frames present
- [ ] Plugin worlds loaded where supported
- [ ] No unexpected newly generated dimension
- [ ] Backup retained after launch

If a dimension appears reset, stop the server immediately. The data may still exist in a folder the new software is not loading.
