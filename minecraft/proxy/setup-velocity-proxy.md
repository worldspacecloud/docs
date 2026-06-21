---
title: "How to Set Up and Install a Velocity Proxy"
description: "Connect multiple Minecraft: Java Edition servers behind one public address using Velocity."
game: "minecraft-java"
category: "proxy"
slug: "setup-velocity-proxy"
updated: "2026-06-21"
author: "WorldSpace Docs Team"
---

# How to Set Up and Install a Velocity Proxy

Velocity is a proxy: it accepts player connections and routes them to backend Minecraft servers. It does not contain a playable world by itself.

## What you need

- One WorldSpace server for the Velocity proxy
- One or more separate backend Minecraft servers
- A unique allocation for every server
- Backend software compatible with your selected forwarding mode
- Access to **Files**, **Startup**, **Network**, and **Console**

Velocity requires a current Java runtime. Use the minimum specified by the current Velocity release; modern releases require Java 21 or newer.

## Install Velocity

1. Create a backup if reusing an existing server.
2. Stop the proxy server.
3. Download the latest stable Velocity JAR from the official PaperMC download page.
4. Upload it to `/` and name it `server.jar`, or set the JAR variable in **Startup** to its exact filename.
5. Select a compatible Java runtime in **Startup**.
6. Start the server once to generate files.
7. Stop it after `velocity.toml` and the forwarding secret file appear.

## Add backend servers

Open `velocity.toml` and configure the `[servers]` section with each backend's assigned address:

```toml
[servers]
lobby = "BACKEND_IP:BACKEND_PORT"
survival = "BACKEND_IP:BACKEND_PORT"
try = [
  "lobby"
]
```

Use the internal/private address provided by WorldSpace when one is available for server-to-server traffic. Otherwise use the assigned backend allocation and ensure it is protected from direct public access.

## Configure player-information forwarding

For modern Paper-compatible backends, use Velocity's modern forwarding when supported.

In `velocity.toml`:

```toml
player-info-forwarding-mode = "modern"
forwarding-secret-file = "forwarding.secret"
```

Copy the exact secret from `forwarding.secret` into the relevant Velocity forwarding setting on every backend server. The location depends on the backend software and version.

Then configure each backend so it expects proxy connections. Do not mix Velocity modern forwarding with BungeeCord forwarding settings.

For Fabric backends, install a maintained forwarding mod that supports Velocity's selected mode when required.

## Authentication layout

- The public Velocity proxy performs player authentication.
- Backends are configured for proxy forwarding and may use offline mode as required by the forwarding setup.
- Backends must be network-restricted so players cannot bypass the proxy.

Setting a backend to offline mode without forwarding and network protection is insecure.

## Point players to the proxy

Share only the proxy's primary allocation or a domain that points to it. Do not share backend addresses.

Start backends first, then start Velocity. In the proxy console, confirm that it is listening on the assigned port and that no server entries failed to resolve.

## Test the network

1. Join through the proxy address.
2. Confirm you arrive at the first server in `try`.
3. Use `/server` if enabled to move between backends.
4. Verify skins, UUID-based permissions, IP bans, and player data.
5. Attempt a direct backend connection from an untrusted network; it should not be usable.

## Common problems

### `This server requires you to connect with Velocity`

The backend expects Velocity forwarding, but the proxy mode or secret does not match.

### Players have new inventories or permissions

UUID forwarding is not configured correctly, or players previously joined the backend directly. Fix forwarding before continuing and restore data from backup where needed.

### Cannot connect to a backend

Check its address, port, status, and network restrictions. The proxy must be allowed to reach the backend.

### `Unable to authenticate player`

Review which layer has authentication enabled and confirm the forwarding mode. Do not randomly toggle online mode on both layers.

## Security checklist

- [ ] Proxy is the only public player entry point
- [ ] Modern forwarding and matching secret configured where supported
- [ ] Backends restricted from direct access
- [ ] Separate secret kept private
- [ ] Only proxy-compatible plugins installed on the proxy
- [ ] Backups created before UUID/authentication changes
