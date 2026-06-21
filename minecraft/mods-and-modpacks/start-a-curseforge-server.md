---
title: "How to Start a CurseForge Minecraft Server"
description: "Install a CurseForge modpack by using its dedicated server pack and matching client profile."
game: "minecraft-java"
category: "mods-and-modpacks"
slug: "start-a-curseforge-server"
updated: "2026-06-21"
author: "WorldSpace Docs Team"
---

# How to Start a CurseForge Minecraft Server

CurseForge modpacks specify a Minecraft version, mod loader, mod list, and configuration. The safest installation method is the pack author's dedicated **server pack**.

## Choose the correct pack release

On the modpack page, record:

- Pack name and release version
- Minecraft version
- Loader and loader version
- Whether the release is stable, beta, or alpha
- Required memory or special startup notes

All players should install the same modpack release in the CurseForge app or another compatible launcher.

## Download the server pack

Open the selected release's additional files and look for a file named `Server Pack`, `Server Files`, or similar.

Do not upload the normal client export unless the author explicitly says it is also the server package. Client exports may omit libraries and may include client-only mods.

## Prepare the files

1. Extract the server pack on your computer.
2. Read `README`, `ServerStart`, or installation notes.
3. Run the included installer locally only when the author requires it to generate libraries.
4. Accept the Minecraft EULA only after reading it.
5. Remove local logs, crash reports, and unnecessary client-only files.
6. Confirm the pack's launch target and Java requirement.
7. Compress the prepared server contents so the files are at the top level of the ZIP.

## Upload to WorldSpace

1. Back up the current server.
2. Stop it.
3. Use a clean server directory when replacing an unrelated pack.
4. Upload the ZIP using SFTP.
5. Extract it into `/`.
6. Open **Startup** and select the required Java runtime.
7. Set the expected JAR or launch target if the server template exposes that variable.
8. Start the server and read the full console output.

If the pack relies on a generated `run.sh`, argument file, or installer-specific launch method that is not available in **Startup**, contact WorldSpace support and provide the pack's official server instructions and download page.

## First start

The first start may take longer while libraries, configs, and spawn chunks are prepared. Do not restart repeatedly unless the console has stopped with a clear error.

When ready:

1. Join with the exact matching client pack.
2. Test quests, dimensions, recipes, and world generation.
3. Set the server address in the client profile instructions for your players.
4. Create a clean post-install backup.

## Updating the modpack

1. Read the author's update notes.
2. Back up the complete server.
3. Download the matching new server pack.
4. Compare folders rather than overwriting blindly.
5. Preserve world, player data, server-specific properties, and any files the author says to keep.
6. Replace mods/configs/scripts as instructed.
7. Update every player's client profile.
8. Test on a copy before updating the live server.

## Common problems

### The server pack has no runnable JAR

It may require a local installation step to generate libraries, or a launch script that uses an argument file. Follow the included README.

### A client-only mod crashes the server

Use the official server pack. If the pack author included the file by mistake, report it and remove only after confirming the mod is client-side.

### Players cannot join because mods differ

Confirm the exact pack release, not only the pack name. Optional client changes should not add content mods that alter registries.

### The server runs out of memory

Use the memory recommendation from the pack author and review console activity. More memory does not fix an incompatible or broken mod combination.
