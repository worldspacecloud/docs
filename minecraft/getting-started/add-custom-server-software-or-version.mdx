---
title: "Add Custom Server Software or Version to Your Server"
description: "Run a custom Minecraft server JAR or a version that is not included in the standard version selector."
game: "minecraft-java"
category: "getting-started"
slug: "add-custom-server-software-or-version"
updated: "2026-06-21"
author: "WorldSpace Docs Team"
---

# Add Custom Server Software or Version to Your Server

Use this method when the desired server software or build is not available in **Startup**. It works best for single-JAR software such as Paper forks and for pre-generated server packs.

> **Back up first.** Replacing server software can modify world files, configuration, plugin data, and startup requirements.

## Before you begin

1. Create and download a full backup.
2. Stop the server.
3. Confirm the required Minecraft and Java versions on the software's official documentation.
4. Download files only from the official project website or repository.
5. Check whether the download is a runnable server JAR, an installer, or a complete server pack.

## Method A: Upload a runnable server JAR

Use this method for software that provides one executable `.jar` file.

1. Download the required build to your computer.
2. Rename it to a simple name such as `server.jar`.
3. Open **Files** in the WorldSpace Game Panel.
4. Upload the JAR to the server's root directory, shown as `/`.
5. Open **Startup**.
6. Set **Server Jar File**, **JAR File**, or the equivalent variable to `server.jar`.
7. Select the Java version required by the software, if a Java selector is available.
8. Start the server and monitor **Console**.

If the server stops on its first launch because the Minecraft EULA has not been accepted, open `eula.txt`, read the linked terms, and change:

```properties
eula=false
```

to:

```properties
eula=true
```

Then start the server again.

## Method B: Upload a generated server pack

Forge, NeoForge, some modpacks, and some hybrid software use multiple libraries and launch files. Generate or download the **server pack**, not the client-only pack.

1. Prepare the server files on your computer according to the project's official instructions.
2. Remove unnecessary client folders such as screenshots, shader packs, and launcher profiles.
3. Keep the generated `libraries`, `mods`, `config`, and launch-related files.
4. Compress the contents into a `.zip`. The required files should be at the top level of the archive, not hidden inside an extra folder.
5. Upload the archive to `/` using **Files** or SFTP.
6. Use the file menu to unarchive it.
7. Open **Startup** and set the required launch target. Depending on the pack, this may be a JAR name or a generated argument file.
8. Start the server and review the complete console output.

If the pack requires a custom shell command that is not exposed in **Startup**, contact WorldSpace support with the official server-pack instructions. Do not paste commands from unofficial videos without checking what they do.

## Replacing existing software safely

When moving from one plugin-based fork to another, keep the existing world and plugin folders unless the new software says otherwise. When moving between plugin and mod loaders, use a clean directory or test server whenever possible.

Avoid deleting the old JAR immediately. Rename it, for example:

```text
paper-old.jar
```

This makes rollback easier, although the backup remains the authoritative recovery point.

## Common startup errors

### `Unable to access jarfile`

The filename in **Startup** does not exactly match the uploaded file. Check spelling, capitalization, and the `.jar` extension.

### `UnsupportedClassVersionError`

The selected Java runtime is too old for the JAR. Choose the Java version required by the software.

### Missing libraries or main class

You uploaded an installer or client pack instead of a runnable server package, or did not upload all generated libraries. Rebuild the server pack from the official installer.

### The server starts as Vanilla

The startup variable still points to the old JAR, or the uploaded JAR was renamed incorrectly.

### Files are inside an extra folder

Move the contents of that folder to `/`. The server's main JAR, `server.properties`, and world folders normally belong in the root directory.

## Roll back

1. Stop the server.
2. Restore the full backup created before the change.
3. Restore the previous Java and startup settings.
4. Start the server and verify the version in **Console**.

## Related guides

- [Changing the Server Version](./changing-the-server-version.md)
- [How to Pick the Best Server Software](./how-to-pick-the-best-server-software.md)
- [How to Set Up a Minecraft Fabric Server](../mods-and-modpacks/setup-a-fabric-server.md)
