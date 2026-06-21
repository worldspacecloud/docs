---
title: "How to Change Your Server Icon"
description: "Add a custom 64×64 PNG icon to the Java Edition multiplayer server list."
game: "minecraft-java"
category: "customization"
slug: "change-server-icon"
updated: "2026-06-21"
author: "WorldSpace Docs Team"
---

# How to Change Your Server Icon

A server icon appears next to your server name in the Minecraft: Java Edition multiplayer list.

## Image requirements

The file must be:

- Exactly `64 × 64` pixels
- PNG format
- Named exactly `server-icon.png`
- Stored in the server root directory `/`

The filename is case-sensitive. Files such as `Server-Icon.png`, `server-icon.jpg`, or `server-icon.png.png` will not work.

## Add the icon

1. Create or resize your image to 64×64 pixels.
2. Export it as PNG with the name `server-icon.png`.
3. Stop the server.
4. Open **Files**.
5. Upload `server-icon.png` to `/`, next to `server.properties`.
6. Start the server.
7. Refresh the multiplayer server list.

## Design tips

- Use a simple shape that remains recognizable at small size.
- Keep important elements away from the edges.
- Use transparency only where it improves readability.
- Preview the image at 64×64 rather than judging a large original.

## Troubleshooting

### The old icon remains

Minecraft may cache server-list information. Refresh the list, restart the client, or remove and re-add the saved server entry.

### No icon appears

Check the image dimensions, filename, format, and location. Make sure it was not uploaded into the world folder.

### The image looks stretched or blurry

Crop the source image to a square before resizing. Do not stretch a rectangular image directly to 64×64.

### The panel hides file extensions

Verify the real filename on your computer. Windows may display `server-icon.png` while the actual file is `server-icon.png.png`.
