---
title: "How to Secure Your Server"
description: "Protect your Minecraft server, panel account, files, and players with practical security controls."
game: "minecraft-java"
category: "getting-started"
slug: "how-to-secure-your-server"
updated: "2026-06-21"
author: "WorldSpace Docs Team"
---

# How to Secure Your Server

A secure Minecraft server uses several layers: protected panel access, authenticated player accounts, restricted backend ports, safe plugins, and recoverable backups. The steps below cover the most important controls for a new server.

## 1. Protect your WorldSpace account

- Use a unique password that you do not use on any other website.
- Enable two-factor authentication when it is available in your account settings.
- Never send your password, session cookie, backup link, or SFTP password to another person.
- Give staff their own sub-user account from **Users** instead of sharing the owner account.
- Grant only the permissions each person needs. A builder usually does not need access to **Startup**, **Backups**, or user management.

Remove old staff accounts immediately when they leave your team.

## 2. Keep authenticated player access enabled

For a normal public Java server, keep this value in `server.properties`:

```properties
online-mode=true
```

This allows the server to verify player identities. Turning it off permits identity spoofing unless the server is correctly protected behind a configured proxy. Never disable it simply to fix a connection error.

For a private server, also enable the allowlist:

```properties
white-list=true
enforce-whitelist=true
```

Then use **Console**:

```text
whitelist on
whitelist add PlayerName
whitelist list
```

## 3. Secure proxy networks correctly

When using Velocity or BungeeCord, players should connect only to the proxy. Backend game servers must not be directly reachable by untrusted players.

- Use a separate allocation/port for each server.
- Configure the forwarding mode and secret exactly as required by the proxy.
- Keep authentication enabled on the public proxy.
- Restrict backend access using the hosting network/firewall options available to your service.
- Do not publish backend addresses.

A forwarding secret improves verification, but it does not replace network restrictions.

## 4. Install trusted software only

Download server JARs, plugins, mods, and modpacks from official project pages or established repositories.

Before uploading a file:

- Confirm it supports your exact Minecraft version and loader.
- Read recent issue reports and release notes.
- Avoid reuploaded or “premium leaked” plugins.
- Remove abandoned components when a maintained replacement exists.
- Update security-sensitive software promptly, but back up before every update.

Plugins and mods run code on your server. Treat them like applications, not harmless configuration files.

## 5. Create a recovery plan

A backup is useful only when it can be restored.

1. Create automatic backups on a schedule appropriate for your server activity.
2. Keep several generations instead of overwriting one file.
3. Download important backups to a separate device or cloud storage.
4. Test a restore on a spare server after major changes.
5. Keep a clean copy from before every version, modpack, or proxy migration.

## Additional hardening

### Limit administrative access

Use operator permissions only for trusted administrators. Prefer a permissions plugin for granular access instead of giving every staff member full operator status.

Review operators with:

```text
op list
```

Remove one with:

```text
deop PlayerName
```

### Avoid exposing sensitive files

Never share these publicly:

- SFTP credentials
- Proxy forwarding secrets
- Database passwords
- Panel API keys
- Full logs containing player IP addresses
- Backups containing plugin configuration or user data

### Review the console

Watch for repeated login failures, unknown plugin messages, unexpected operator grants, and unexplained file changes. If you suspect compromise:

1. Stop the server.
2. Change account and SFTP passwords.
3. Remove unknown sub-users.
4. Preserve logs and a copy of the current files.
5. Restore a known-good backup or rebuild from trusted files.
6. Update all software before reopening.

## Security checklist

- [ ] Unique account password
- [ ] Two-factor authentication enabled when available
- [ ] Individual staff accounts with minimal permissions
- [ ] `online-mode=true` unless a secured proxy design requires otherwise
- [ ] Allowlist enabled for private servers
- [ ] Backend servers hidden behind the proxy
- [ ] Plugins and mods downloaded from trusted sources
- [ ] Multiple tested backups stored separately
