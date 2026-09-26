# ilyStream downloads

Official Windows installers for [ilyStream](https://www.ilystream.app/).

[Download the latest release](https://github.com/ilydrw/ilyStream-Releases/releases/latest)

## Requirements

- Windows 11 (build 22000 or newer), Intel or AMD x64.
- Administrator access for installation and the optional virtual camera.
- The installer includes the required Microsoft Visual C++ runtime.

The Windows installer is unsigned. Windows may show an unknown-publisher or
SmartScreen warning. Check the downloaded file against the `.sha256` asset
published with its release.

Starting with v0.1.1, automatic updates authenticate release metadata with the
public key embedded in the app and verify the installer size and SHA-256. With
update checks enabled, newer versions download in the background and install
after the app closes and saves settings. Windows asks for administrator approval;
other ilyStream copies must be closed. Existing v0.1.0 users need to install
v0.1.1 manually once to enable future automatic updates.

On first launch, ilyStream guides you through appearance, animation preferences,
and choosing a starting workspace. Setup and account connections are optional.

Native settings are stored separately from the older Electron app. This release
does not automatically migrate Electron settings. Uninstall keeps native user
settings; installing a newer native version preserves them.

## Release files

Each release includes a versioned Windows installer, its SHA-256 checksum,
and `latest-windows.json` with the version, size, platform, and signing status.
Releases from v0.1.1 also include `latest-windows.json.sig`, the detached
RSA-3072/SHA-256 signature required by the updater. This update signature is
separate from Windows Authenticode publisher signing.
The source code is maintained separately in a private repository.

[Getting started](https://www.ilystream.app/docs/) ·
[Release history](https://github.com/ilydrw/ilyStream-Releases/releases)
