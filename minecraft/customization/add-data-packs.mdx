---
title: "How to Add Data Packs to Your Server"
description: "Install a Java Edition data pack to add recipes, functions, loot tables, structures, and gameplay rules."
game: "minecraft-java"
category: "customization"
slug: "add-data-packs"
updated: "2026-06-21"
author: "WorldSpace Docs Team"
---

# How to Add Data Packs to Your Server

Data packs change server-side gameplay without a plugin loader. They can add functions, recipes, advancements, loot tables, tags, structures, and world-generation data.

## Before you begin

- Confirm the data pack supports your exact Minecraft version.
- Back up the world.
- Read the author's installation notes for required dependencies or experimental features.
- Test world-generation packs on a copy first; removing them later may leave generated content behind.

## Find the active world folder

Open `server.properties` and check:

```properties
level-name=world
```

The data pack folder is:

```text
/world/datapacks
```

Replace `world` with the actual `level-name` value.

## Install the data pack

1. Stop the server.
2. Open **Files** and navigate to the active world's `datapacks` folder.
3. Upload the data pack `.zip` or extracted folder.
4. Confirm `pack.mcmeta` is directly inside the ZIP/folder, not one directory deeper.
5. Start the server.

For large packs, upload with SFTP.

## Verify installation

Run in **Console**:

```text
datapack list
```

Enabled packs appear in the enabled list. If a pack is available but disabled, use its exact identifier:

```text
datapack enable "file/example-pack.zip"
```

Many packs initialize automatically on startup. Check `logs/latest.log` for messages from the pack.

## Reloading

The `/reload` command reloads datapacks and functions, but it can be resource-intensive and may not reset every system cleanly. A full restart is safer after installation or a major update.

## Updating a data pack

1. Read the pack's migration notes.
2. Create a world backup.
3. Stop the server.
4. Replace the old pack with the new version.
5. Keep only one copy; duplicate versions may both load.
6. Start the server and check console errors.
7. Run any migration function supplied by the author.

## Removing a data pack

Some packs include an uninstall function that removes scoreboards, storage, teams, or generated entities. Run it before deleting the file when the author provides one.

Then:

1. Back up the world.
2. Stop the server.
3. Remove the pack from `datapacks`.
4. Start and review the log.

World-generation content already saved in chunks will not automatically disappear.

## Common problems

### `Made for an older/newer version`

The `pack_format` does not match the server version. Obtain the correct release. Manually changing the number does not make incompatible commands or data formats work.

### The pack does not appear

The file is in the wrong world's folder, or `pack.mcmeta` is inside an extra directory. Open the archive and correct the layout.

### Functions show command errors

The pack uses command syntax from another Minecraft version or depends on a missing companion resource pack/data pack.

### The server lags after installation

Some packs run commands every tick. Check the author's performance notes and test without the pack on a copy before removing it from production.
