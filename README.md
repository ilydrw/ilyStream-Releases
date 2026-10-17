# ilyStream downloads

Official Windows installers and DeskThing companion bundles for
[ilyStream](https://ilystream.app/).

[Download the latest release](https://github.com/ilydrw/ilyStream-Releases/releases/latest)

## Version 0.2.0

| Download | Checksum |
| --- | --- |
| [Windows installer](https://github.com/ilydrw/ilyStream-Releases/releases/download/v0.2.0/ilyStream-Setup-0.2.0-windows-x64.exe) | [SHA-256](https://github.com/ilydrw/ilyStream-Releases/releases/download/v0.2.0/ilyStream-Setup-0.2.0-windows-x64.exe.sha256) |
| [DeskThing companion ZIP](https://github.com/ilydrw/ilyStream-Releases/releases/download/v0.2.0/ilystream-deskthing-0.2.0.zip) | [SHA-256](https://github.com/ilydrw/ilyStream-Releases/releases/download/v0.2.0/ilystream-deskthing-0.2.0.zip.sha256) |

[Website downloads and setup](https://ilystream.app/download) ·
[Version 0.2.0 release notes](https://github.com/ilydrw/ilyStream-Releases/releases/tag/v0.2.0)

Windows installer: **137,670,160 bytes**. SHA-256:

```text
81297525356068b9a4769db8559068d2f40705f4f089e0114da42fe395a72559
```

This Windows preview expands capture-card, chat, speech, and widget controls,
improves keyboard and accessibility support, adds private in-app bug reports,
and hardens local storage and remote connections. Install the matching DeskThing
companion v0.2.0 alongside the desktop update.

## Requirements

- Windows 11 (build 22000 or newer), Intel or AMD x64.
- Administrator access for installation and the optional virtual camera.
- The installer includes the required Microsoft Visual C++ runtime.

The Windows installer is unsigned. Windows may show an unknown-publisher or
SmartScreen warning. Check the downloaded file against the `.sha256` asset
published with its release.

Starting with v0.1.1, automatic updates authenticate release metadata with the
public key embedded in the app and verify the installer size and SHA-256. With
update checks enabled, newer versions download in the background. Choose
**Restart to update** in the notification center to save settings and install;
an ordinary close does not install a prepared update. If saving fails, the app
stays open so you can retry. Windows asks for administrator approval;
other ilyStream copies must be closed. Existing v0.1.0 users must install a
current native version manually once to enable future automatic updates.

On first launch, ilyStream guides you through appearance, animation preferences,
and choosing a starting workspace. Setup and account connections are optional.

Native settings are stored separately from the older Electron app. This release
does not automatically migrate Electron settings. Uninstall keeps native user
settings; installing a newer native version preserves them. Webhook credentials
and managed recovery copies are encrypted for the current Windows user.
Copying those preference files to another account or PC cannot restore their
secrets. Portable show exports continue to remove and disable webhooks.

## DeskThing companion

Import the companion ZIP through DeskThing, or add this public repository to
DeskThing's app discovery. The release includes `ilystream.json` discovery
metadata and the `ilystream.zip` install alias. Use DeskThing server 0.11.13 or
later and client 0.11.2 or later.

Upgrading from companion 0.0.28 requires importing a current companion ZIP
(v0.1.8 or newer) once through DeskThing. Its older update address points to the
previous source repository, so it cannot discover this release automatically.
The app ID remains `ilystream`; the new bundle uses this public repository for
future update discovery.

On the PC running both ilyStream and the DeskThing server, open
**Connect → Hardware → DeskThing**, choose **Switch on Remote control** if
needed, then **Pair new device**. In the companion's DeskThing settings, use
`127.0.0.1:3738` (or the configured remote-control port) and enter the displayed
six-digit code. The DeskThing server sends these requests from the PC; the
physical device does not connect to its own loopback address. Pairing does not
need a cloud account.

Companion v0.2.0 keeps explicit HTTPS addresses and explains when a LAN address
requires TLS. A connection from another computer must validate the desktop's
controller CA using a supported trust configuration; certificate validation is
never bypassed. For the ordinary same-PC setup, use the loopback address above.
Previous device grants without an identity binding must be paired again.

Chat filters individual TikTok Like rows before history limits so bursts do not
crowd out messages. Aggregate Likes statistics remain available.

[DeskThing installation and pairing guide](https://ilystream.app/docs/connect/deskthing/)

## Phone controller

On the PC, open **Settings → Network**, enable **Remote control**, and choose
**Phone controller → Pair phone**. Phone and LAN controller traffic now requires
HTTPS with this installation's controller certificate.

1. Choose **Copy certificate download link** and open it on the phone. The public
   certificate download is the only unencrypted LAN resource.
2. Compare every byte of the downloaded certificate's **SHA-256** fingerprint
   with **Certificate SHA-256** on the PC before installing it as a trusted CA.
   Do not install a mismatched certificate or bypass an HTTPS warning.
3. Use **Copy controller address**, open that HTTPS address on the phone, and
   enter the temporary six-digit code and a device name. Choose **Pair and
   connect**. The code expires after five minutes and can be used once; the copied
   address contains no token. Request a new code if certificate setup takes longer.

Keep the phone and PC on the same trusted network and allow the displayed remote
port through Windows Firewall. Use the PC's LAN address; `127.0.0.1` on a phone
refers to the phone itself. Device access can be revoked under Network settings.
Existing device grants without an identity binding require pairing again.
Resetting the controller certificate also revokes paired devices and requires
verifying and trusting the replacement certificate.

The controller provides live chat and application state, scene Take/Cut, mixer,
source, recording, replay, soundboard, and voice controls. Output labels follow
the computer's actual state; a queued command does not mean an output is active.
The computer runs the broadcast. Phone camera/microphone input is separate.

[Phone controller and certificate setup](https://ilystream.app/docs/connect/phone-controller/)

## Release files

Each release includes a versioned Windows installer, its SHA-256 checksum,
and `latest-windows.json` with the version, size, platform, and signing status.
Releases from v0.1.1 also include `latest-windows.json.sig`, the detached
RSA-3072/SHA-256 signature required by the updater. This update signature is
separate from Windows Authenticode publisher signing.
Companion releases also include the versioned ZIP and checksum, `ilystream.zip`,
`ilystream.json`, and `SHA256SUMS.txt`.
The source code is maintained separately in a private repository.

This remains a preview. Local checks do not establish compatibility with every
physical capture/audio device, plugin, DeskThing device, or live platform.
Phone trust, touch input, Wi-Fi reachability, and firewall setup depend on the
user's network. The optional OBS workspace plugin is a separate distribution.

[Getting started](https://ilystream.app/docs/) ·
[Release history](https://github.com/ilydrw/ilyStream-Releases/releases)
