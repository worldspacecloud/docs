---
title: "How to Set Up and Install a BungeeCord Proxy"
description: "Build a BungeeCord network with multiple backend Java servers and correct IP forwarding."
game: "minecraft-java"
category: "proxy"
slug: "setup-bungeecord-proxy"
updated: "2026-06-21"
author: "WorldSpace Docs Team"
---

# How to Set Up and Install a BungeeCord Proxy

BungeeCord routes players between multiple Minecraft: Java Edition backend servers. It is commonly used for established networks and plugins that specifically depend on the BungeeCord API. For a new network without legacy requirements, also evaluate Velocity.

## Requirements

- A dedicated proxy server
- At least one backend Spigot/Paper-compatible server
- A unique allocation for every server
- Backups of all existing player and permissions data
- A plan to prevent direct backend connections

## Install BungeeCord

1. Stop the server chosen for the proxy.
2. Download `BungeeCord.jar` from the official SpigotMC build source.
3. Upload it to `/`.
4. In **Startup**, set the JAR filename to `BungeeCord.jar` or rename the file to the expected JAR name.
5. Start once to generate `config.yml`.
6. Stop the proxy.

## Configure listeners

Open `config.yml`. In the `listeners` section, set the host to the proxy's assigned allocation and configure player limits, priorities, MOTD, and query options as required.

Example structure:

```yaml
listeners:
- host: 0.0.0.0:25577
  max_players: 100
  priorities:
  - lobby
  motd: 'A WorldSpace Network'
```

Use the port assigned in **Network**, not an arbitrary example port.

## Add backend servers

In the `servers` section:

```yaml
servers:
  lobby:
    address: BACKEND_IP:BACKEND_PORT
    motd: 'Lobby'
    restricted: false
  survival:
    address: BACKEND_IP:BACKEND_PORT
    motd: 'Survival'
    restricted: false
```

The names under `priorities` must exactly match entries under `servers`.

## Enable IP forwarding

In the proxy's `config.yml`:

```yaml
ip_forward: true
online_mode: true
```

On each compatible backend:

1. Enable BungeeCord forwarding in the server software's configuration.
2. Set the backend's `online-mode=false` only as required by the proxy design.
3. Restrict the backend so players cannot connect directly.

BungeeCord's legacy forwarding does not safely protect an internet-exposed offline-mode backend by itself. Network restrictions are essential.

## Start order and testing

1. Start every backend server.
2. Confirm each backend reaches its ready state.
3. Start BungeeCord.
4. Join using only the proxy address.
5. Confirm correct UUIDs, skins, IP addresses, permissions, and inventories.
6. Test movement between servers.

## Plugins

Proxy plugins belong in the proxy's `/plugins` folder and must be built for BungeeCord. Bukkit/Paper plugins belong on the backend servers. Some systems require a component on both layers; follow the plugin's official installation guide.

Restart the proxy after adding or updating plugins. Avoid hot-reload commands on production networks.

## Common problems

### `Could not connect to a default or fallback server`

The server named in `priorities` is stopped, unreachable, or misspelled.

### Player UUIDs changed

IP forwarding or backend proxy support is not configured correctly. Fix the configuration before allowing normal play and restore affected data from backup if necessary.

### Players bypass the proxy

Backend allocations are publicly reachable. Apply available network restrictions and never publish those addresses.

### YAML parsing error

`config.yml` uses spaces for indentation. Do not use tabs. Restore the generated file and reapply changes carefully.

## Migration note

Do not switch an active network between BungeeCord and Velocity forwarding without a maintenance window and player-data backup. Authentication or forwarding mistakes can cause players to appear under different UUIDs.
