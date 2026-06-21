---
title: "Upload or Download Your World from Your Server"
description: "Transfer a complete Java Edition world between your computer and WorldSpace without losing dimensions or player data."
game: "minecraft-java"
category: "worlds"
slug: "upload-or-download-your-world"
updated: "2026-06-21"
author: "WorldSpace Docs Team"
---

# Upload or Download Your World from Your Server

A complete world transfer must include the level data, region files, player data, and every dimension used by the server software.

## Download your world

1. Ask players to disconnect.
2. Run in **Console**:

```text
save-all flush
```

3. Stop the server.
4. Open `server.properties` and note the `level-name` value.
5. Download that world folder with SFTP.
6. Also download any separate Nether, End, or plugin-world folders used by your software.
7. Wait until the SFTP queue has no failed transfers.
8. Compress the local copy and store it safely.

Do not download an actively changing world if you need a consistent backup. Files can be captured at different save moments.

## Identify a valid Java world

The main world folder normally contains files/folders such as:

```text
level.dat
region/
playerdata/
data/
entities/
poi/
```

The exact list varies by version. The folder containing `level.dat` is usually the folder that should match `level-name`.

## Upload an existing world

1. Stop the server.
2. Create a backup of the current server files.
3. Prepare the world on your computer.
4. Remove an extra wrapper directory if present. `level.dat` should be directly inside the folder you plan to upload.
5. Rename the folder to a simple name using letters, numbers, hyphens, or underscores, for example `survival_world`.
6. Upload it to `/` with SFTP.
7. Open `server.properties` and set:

```properties
level-name=survival_world
```

8. Upload related dimension folders when required by the source/target software layout.
9. Start the server and monitor **Console**.
10. Join and verify spawn, dimensions, inventories, and builds.

## Upload a single-player world

A Java single-player save can normally be uploaded as a server world. Copy the save folder from the Java Edition `saves` directory. The server ignores client-only files that are not needed.

Before opening the world publicly:

- Check game mode and difficulty.
- Review cheats/operator expectations.
- Move the owner from an unsafe location if necessary.
- Confirm datapacks are present in `world/datapacks`.

## Large worlds

For large transfers:

- Use SFTP instead of the browser uploader.
- Compress many small files before upload when possible.
- Ensure enough disk space for both the archive and extracted copy.
- Delete the uploaded archive after successful extraction and verification.
- Keep the server stopped until the transfer completes.

## Common problems

### A new world is generated

`level-name` does not match the uploaded folder, the folder is nested one level too deep, or capitalization differs.

### The overworld works but Nether/End is new

The dimension folders are missing or stored in the layout expected by different server software. Stop the server and compare the source and target software's migration instructions.

### Players have empty inventories

You may have uploaded only region files, not `playerdata`, or the server is using different authenticated UUIDs. Restore the complete world and verify authentication settings.

### Upload fails near the end

Check disk quota and failed transfer items. Remove temporary archives or old backups only after downloading anything important.

## Keep the original

Do not delete the source world until the uploaded copy has been tested over several restarts. Keep at least one off-site archive that was created while the source server was stopped.
