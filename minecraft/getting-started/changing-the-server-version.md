---
title: "Changing the Server Version"
description: "Change your Minecraft: Java Edition version safely while protecting your world and configuration."
game: "minecraft-java"
category: "getting-started"
slug: "changing-the-server-version"
updated: "2026-06-21"
author: "WorldSpace Docs Team"
---

# Changing the Server Version

Changing versions lets you update to new Minecraft features, return to an older release, or match the version required by a plugin or modpack. A version change can also change the Java runtime, file format, and software build your server needs, so always prepare a rollback first.

> **Important:** Never downgrade a world without a tested backup. Newer Minecraft versions may write blocks, entities, or world data that older versions cannot understand.

## Before you begin

1. Ask every player to disconnect.
2. Run `save-all flush` in **Console** and wait for the save confirmation.
3. Stop the server.
4. Open **Backups** and create a full backup. Download a second copy if the world is important.
5. Write down the current Minecraft version, server software, and Java version shown in **Startup**.

## Change the version

1. Open your server in the WorldSpace Game Panel.
2. Go to **Startup**.
3. Find the variable named **Minecraft Version**, **Server Version**, **Build**, or similar. The exact name depends on the installed server software.
4. Select or enter the target version.
5. If you are also changing software, update the software or JAR variable as described in [Add Custom Server Software or Version](./add-custom-server-software-or-version.md).
6. Start the server and watch **Console** until the server reports that startup is complete.

Some server templates download the selected version automatically. Others require a reinstall after changing the version variable. If the panel displays a reinstall notice, confirm that your backup is complete before using **Settings → Reinstall Server**.

## Check Java compatibility

Minecraft versions use different Java releases. If startup fails with messages such as `UnsupportedClassVersionError`, `class file version`, or `A JNI error has occurred`, open **Startup** and choose a compatible Java image/runtime if that option is available.

As a general guide:

| Minecraft generation | Common Java requirement |
|---|---:|
| 1.16.5 and older | Java 8–16, depending on the exact version |
| 1.17 | Java 16 or newer |
| 1.18–1.20.4 | Java 17 |
| 1.20.5–1.21.x | Java 21 |
| 26.1 and newer | Java 25 or newer |

Custom server software may set a newer minimum than Vanilla. Follow the software developer's current documentation when it differs from the table.

## Verify the change

After the server starts:

1. Check the first lines in **Console** for the Minecraft and software versions.
2. Join the server with the matching client version.
3. Test the Nether, End, inventories, commands, plugins, and datapacks.
4. Keep the old backup until the server has run normally for several days.

## Common problems

### The server creates a new world

Check `level-name` in `server.properties`. It must match the folder containing your existing world. Folder names are case-sensitive.

### Plugins or mods no longer load

Plugins and mods are version-specific. Update each one from its official source, and remove components that do not support the target version. Do not repeatedly restart a crashing server with incompatible mods installed.

### The world will not open after a downgrade

Stop the server and restore the pre-change backup. Downgrading world data is not reliably reversible.

### The selected version is not listed

Use a custom server JAR or generated server pack. See [Add Custom Server Software or Version](./add-custom-server-software-or-version.md).

## Recommended update workflow

For production servers, first copy the backup into a temporary test server. Update the test copy, verify all plugins and worlds, and only then repeat the change on the live server.
