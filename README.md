# ilyStream downloads

Official Windows installers and DeskThing companion bundles for
[ilyStream](https://www.ilystream.app/).

[Download the latest release](https://github.com/ilydrw/ilyStream-Releases/releases/latest)

## Version 0.1.8

| Download | Checksum |
| --- | --- |
| [Windows installer](https://github.com/ilydrw/ilyStream-Releases/releases/download/v0.1.8/ilyStream-Setup-0.1.8-windows-x64.exe) | [SHA-256](https://github.com/ilydrw/ilyStream-Releases/releases/download/v0.1.8/ilyStream-Setup-0.1.8-windows-x64.exe.sha256) |
| [DeskThing companion ZIP](https://github.com/ilydrw/ilyStream-Releases/releases/download/v0.1.8/ilystream-deskthing-0.1.8.zip) | [SHA-256](https://github.com/ilydrw/ilyStream-Releases/releases/download/v0.1.8/ilystream-deskthing-0.1.8.zip.sha256) |

[Website downloads and setup](https://www.ilystream.app/download) ·
[Version 0.1.8 release notes](https://github.com/ilydrw/ilyStream-Releases/releases/tag/v0.1.8)

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
other ilyStream copies must be closed. Existing v0.1.0 users need to install
v0.1.1 manually once to enable future automatic updates.

On first launch, ilyStream guides you through appearance, animation preferences,
and choosing a starting workspace. Setup and account connections are optional.

Native settings are stored separately from the older Electron app. This release
does not automatically migrate Electron settings. Uninstall keeps native user
settings; installing a newer native version preserves them.

## DeskThing companion

Import the companion ZIP through DeskThing, or add this public repository to
DeskThing's app discovery. The release includes `ilystream.json` discovery
metadata and the `ilystream.zip` install alias. Use DeskThing server 0.11.13 or
later and client 0.11.2 or later.

Upgrading from companion 0.0.28 requires importing the 0.1.8 ZIP once through
DeskThing. Its older update address points to the previous source repository,
so it cannot discover this release automatically. The app ID remains `ilystream`;
the new bundle uses this public repository for future update discovery.

In the Windows app, open **Connect → Hardware → DeskThing**, enable **Remote
control**, and choose **Pair new device**. Enter the displayed address and
six-digit code in the companion. The device and PC use your local network;
pairing does not need a cloud account.

[DeskThing installation and pairing guide](https://www.ilystream.app/docs/connect/deskthing/)

## Release files

Each release includes a versioned Windows installer, its SHA-256 checksum,
and `latest-windows.json` with the version, size, platform, and signing status.
Releases from v0.1.1 also include `latest-windows.json.sig`, the detached
RSA-3072/SHA-256 signature required by the updater. This update signature is
separate from Windows Authenticode publisher signing.
Companion releases also include the versioned ZIP and checksum, `ilystream.zip`,
`ilystream.json`, and `SHA256SUMS.txt`.
The source code is maintained separately in a private repository.

[Getting started](https://www.ilystream.app/docs/) ·
[Release history](https://github.com/ilydrw/ilyStream-Releases/releases)
