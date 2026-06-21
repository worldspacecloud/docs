---
title: "How to Add Resource Packs to Your Server"
description: "Prompt players to download a server resource pack for custom textures, sounds, models, and UI assets."
game: "minecraft-java"
category: "customization"
slug: "add-resource-packs"
updated: "2026-06-21"
author: "WorldSpace Docs Team"
---

# How to Add Resource Packs to Your Server

A server resource pack lets a Java server offer textures, sounds, models, fonts, and other client assets to players when they join. Players still control the game client, so the server sends a download link rather than reading a pack directly from the server's file manager.

## Prepare the pack

1. Confirm the pack supports the Minecraft version used by the server.
2. Open the `.zip` and verify that `pack.mcmeta` and the `assets` folder are at the top level.
3. Keep the archive as a `.zip`; do not upload a folder link.
4. Test the pack locally from the Minecraft resource-pack menu.

## Host a direct download

Upload the `.zip` to a web host that provides a public HTTPS direct-download URL. The link must return the file itself, not an HTML preview, login page, or advertising page.

Test it in a private browser window. A working link immediately downloads or opens the ZIP response without requiring an account.

## Calculate the SHA-1 hash

A SHA-1 hash lets the client identify the exact file and helps refresh cached copies when you update the pack.

Windows PowerShell or Command Prompt:

```text
certutil -hashfile resource-pack.zip SHA1
```

macOS:

```text
shasum resource-pack.zip
```

Linux:

```text
sha1sum resource-pack.zip
```

Copy the 40-character hash without spaces.

## Configure `server.properties`

1. Stop the server.
2. Open **Files → server.properties**.
3. Set the direct URL and hash:

```properties
resource-pack=https://downloads.example.com/resource-pack.zip
resource-pack-sha1=0123456789abcdef0123456789abcdef01234567
require-resource-pack=false
```

Optional prompt text can be added where supported:

```properties
resource-pack-prompt=This server uses a custom resource pack.
```

Set `require-resource-pack=true` only when the pack is necessary for gameplay. Players who decline a required pack cannot remain connected.

4. Save the file and start the server.

## Test the pack

1. Remove or rename the local cached server pack while testing.
2. Join the server.
3. Accept the resource-pack prompt.
4. Verify textures, sounds, fonts, and custom model data.
5. Test with a second account or clean client profile before publishing.

## Update the pack

When the ZIP contents change:

1. Upload the new ZIP.
2. Calculate a new SHA-1 hash.
3. Replace `resource-pack-sha1`.
4. Restart the server.

Using a new filename or versioned URL, such as `pack-v3.zip`, also helps avoid stale caches.

## Common problems

### The client says the download failed

The URL is not a direct HTTPS file link, the host blocks automated downloads, or the file exceeds a client/version limitation. Open the URL in a private window and inspect the response.

### The pack downloads but does not load

`pack.mcmeta` may be inside an extra folder, its pack format may not match the Minecraft version, or the ZIP is corrupted.

### Players still see the old pack

Update both the hosted file and SHA-1 value. Ask the player to set the server entry's **Server Resource Packs** option to `Enabled` or `Prompt`, then reconnect.

### Special characters break the URL

Use a simple filename and a properly encoded URL. Avoid spaces where possible.
