---
title: "How to Connect to Your Minecraft Server with SFTP"
description: "Use a secure file-transfer client to upload worlds, mods, plugins, and large server files."
game: "minecraft-java"
category: "getting-started"
slug: "how-to-connect-with-sftp"
updated: "2026-06-21"
author: "WorldSpace Docs Team"
---

# How to Connect to Your Minecraft Server with SFTP

SFTP is the secure file-transfer method for your WorldSpace server. Although some apps use “FTP client” as a general label, the connection protocol must be **SFTP**, not plain FTP or FTPS.

## What you need

Install an SFTP-capable client such as FileZilla, WinSCP, Cyberduck, or another trusted application. Then open your server in the WorldSpace Game Panel and go to **Settings** to find:

- SFTP server address
- SFTP port
- Username
- Password instructions

Your SFTP password is normally the password associated with your panel account or the credential shown by the panel. Never send it to another person.

## Connect with FileZilla

1. Open **File → Site Manager**.
2. Select **New Site**.
3. Set **Protocol** to `SFTP - SSH File Transfer Protocol`.
4. Enter the host from **Settings**.
5. Enter the displayed SFTP port. Do not assume port 22.
6. Set **Logon Type** to `Normal` or the secure option supported by your client.
7. Enter the full SFTP username exactly as displayed.
8. Enter your password and connect.
9. Accept the host key only after confirming the host matches the panel information.

The remote server files appear on one side and your local computer files on the other.

## Upload files

- Stop the server before replacing a world, JAR, modpack, or active database file.
- Upload plugins to `/plugins`.
- Upload loader mods to `/mods`.
- Upload a world folder to `/`, then set `level-name` to that folder name.
- Upload configuration files to their original location.
- Keep filenames and capitalization unchanged.

For many small files, compress them into a `.zip`, upload one archive, and extract it from **Files**. This is usually faster and reduces transfer failures.

## Download files

To download a world safely:

1. Run `save-all flush` in **Console**.
2. Stop the server.
3. Download the entire world folder and any related dimension folders.
4. Wait until the transfer queue is empty before restarting.

A completed transfer should have no failed items in the client queue.

## Resume and transfer mode

Use binary/automatic transfer mode. Modern SFTP clients select this automatically. When a large transfer is interrupted, choose **Resume** only when the client confirms the local and remote files match up to the interruption point; otherwise overwrite the incomplete file.

## Common problems

### Authentication failed

Copy the username exactly, including any server-specific suffix. Reset your panel password if necessary and reconnect with the new credentials.

### Connection timed out

Check the SFTP host and custom port shown in **Settings**. A game allocation port is not the same as the SFTP port.

### Too many authentication failures

Delete old saved credentials or SSH keys from the client entry and reconnect using only the expected login method.

### Upload completes but the server cannot see the files

The files may be inside an extra parent folder. In **Files**, confirm that `server.properties`, the server JAR, and world folders are in the expected path.

### Permission denied

Upload only within your server directory. System paths outside the assigned server storage are not accessible.

## Security tips

- Save passwords only on a trusted personal device.
- Remove saved credentials from shared computers.
- Do not post screenshots that reveal the username, host, or port together with account details.
- Disconnect old sessions after changing your password.
