---
title: "How to Set Up a Minecraft Fabric Server"
description: "Install Fabric Loader, Fabric API, and compatible mods on a Minecraft: Java Edition server."
game: "minecraft-java"
category: "mods-and-modpacks"
slug: "setup-a-fabric-server"
updated: "2026-06-21"
author: "WorldSpace Docs Team"
---

# How to Set Up a Minecraft Fabric Server

Fabric is a lightweight mod loader used for custom mod sets, technical servers, and many performance-focused setups.

## Choose versions

Before downloading anything, select:

- Minecraft version
- Fabric Loader version
- Fabric Installer or executable server launcher version
- Fabric API version, when required by your mods

Every mod must support the chosen Minecraft and Fabric versions.

## Method 1: Executable Fabric server launcher

When the official Fabric download page provides an executable server JAR for your target version:

1. Download the server launcher from the official Fabric website.
2. Rename it to `server.jar` if desired.
3. Stop the WorldSpace server and create a backup.
4. Upload the JAR to `/`.
5. Set the **Server Jar File** startup variable to the exact filename.
6. Select the Java version required by the target Minecraft version.
7. Start once to generate files.
8. Read and accept `eula.txt` if you agree to the Minecraft EULA.
9. Start again.

## Method 2: Generate files with the Fabric installer

1. Download the official universal installer to your computer.
2. Select the **Server** tab.
3. Choose the Minecraft and Loader versions.
4. Enable the option to download the Minecraft server JAR when offered.
5. Install into an empty local folder.
6. Compress the generated contents.
7. Upload and extract them into `/`.
8. Set the generated Fabric server launch JAR as the startup JAR.
9. Choose the compatible Java runtime and start.

## Install Fabric API and mods

Many Fabric mods depend on Fabric API, but Fabric Loader itself does not automatically include it.

1. Stop the server.
2. Download Fabric API for the exact Minecraft version when required.
3. Upload it to `/mods`.
4. Upload server-compatible Fabric mods and their dependencies.
5. Start and inspect **Console**.

Do not place Forge, NeoForge, Paper, or Spigot files in the Fabric `mods` folder.

## Player setup

Mods marked as required on both sides must also be installed in each player's Fabric profile. Server-side-only optimization or administration mods may not be required by players.

Publish an exact mod list or launcher profile so players do not guess versions.

## Updating Fabric

Loader, Fabric API, Minecraft, and mods are separate components. Update them deliberately:

1. Create a full backup.
2. Test the target Loader with the current Minecraft version.
3. Update Fabric API and mods to compatible versions.
4. Replace old files rather than keeping duplicates.
5. Update the client profile.
6. Start on a test copy and review warnings.

## Common problems

### `Could not find required mod: fabric-api`

Install the compatible Fabric API file in `/mods`.

### `Mod resolution encountered an incompatible mod set`

Read the dependency tree in the error. One file may require a newer Loader, Minecraft version, Java version, or another mod.

### The server starts as Vanilla

The startup JAR points to the Vanilla JAR rather than the Fabric launcher.

### A mod references client classes

Remove the client-only mod from the server. Keep it only in player profiles if required.

## Useful files

| Path | Purpose |
|---|---|
| `/mods` | Fabric mod JARs |
| `/config` | Shared mod configuration |
| `/world/serverconfig` | World-specific configuration used by some mods |
| `/logs/latest.log` | Current diagnostic log |
