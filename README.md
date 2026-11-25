# OpenWrt build for TP-Link Archer C20 v5

This repository builds an OpenWrt 25.12.6 sysupgrade image using the **official OpenWrt ImageBuilder**.

## Target device

- Model: TP-Link Archer C20 v5
- OpenWrt target: `ramips/mt76x8`
- ImageBuilder profile: `tplink_archer-c20-v5`
- Official profile flash layout: `8MSUmtk`
- Maximum firmware image size: `7616 KiB`

The running router reports board name `tplink,archer-c20-v5` and an 8 MiB MTD layout. The workflow checks the generated image against the 7616 KiB profile limit. It does not write to, connect to, or flash any router.

## Included packages

- LuCI web interface, HTTPS support, and Russian base translation
- PPPoE protocol support
- tcpdump, ethtool, iw, ip-full, curl, ca-bundle, htop
- Device-specific packages selected by the official OpenWrt profile (including its Wi-Fi driver package)

AmneziaWG, Podkop, and sing-box are intentionally not included in this first build. They can be considered separately after checking package availability, flash space, and RAM constraints.

## Build

1. Open the **Actions** tab in this repository.
2. Select **Build OpenWrt 25.12.6 - Archer C20 v5**.
3. Click **Run workflow**.
4. When it finishes, open the run and download the artifact named `openwrt-25.12.6-archer-c20-v5`.

The artifact contains the sysupgrade image, its SHA-256 checksum, and the package manifest when available.

**Important:** A successful build is not permission to flash it. Before any upgrade, independently verify the image, checksum, router backup, and the exact upgrade procedure. Do not write full-flash dumps or factory/calibration data to this public repository.
