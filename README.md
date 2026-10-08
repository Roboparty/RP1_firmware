<a id="top"></a>

# RP1 · Firmware

**Linux BSP, firmware and software package sources for the RoboParty RP1 humanoid.**

This repository is the firmware entry point of the RP1 platform. It gathers the
board support package, the HPM USB-CANFD bridge firmware and the Debian/APT
source repositories used to build and flash a RoboPi compute board.

## Repositories

The sources live in the following submodules:

<table width="100%">
<tr>
<td width="180"><a href="https://github.com/Roboparty/roboparty_build"><strong>roboparty_build</strong></a></td>
<td>BSP build system: kernel, device tree, bootloader and the image/build pipelines.</td>
</tr>
<tr>
<td width="180"><a href="https://github.com/Roboparty/roboparty_EtherCANFD"><strong>EtherCANFD</strong></a></td>
<td>HPM USB-CANFD bridge: firmware and host tooling that expose the robot CAN-FD buses over USB.</td>
</tr>
<tr>
<td width="180"><a href="https://github.com/Roboparty/roboparty_repo"><strong>roboparty_repo</strong></a></td>
<td>APT repository automation: source manifest, Debian package routing and the low-level SDK package sources.</td>
</tr>
</table>

Each submodule is an independent repository with its own build and release
instructions. Start there for subsystem-specific documentation.

## Getting Started

Clone with the submodules in one step:

```bash
git clone --recurse-submodules https://github.com/Roboparty/RP1_firmware.git
cd RP1_firmware
```

If the repository is already cloned, fetch the submodule contents with:

```bash
git submodule update --init --recursive
```

Update the submodules to the latest revision of their tracked branches:

```bash
git submodule update --remote --merge
```

Inspect the current state:

```bash
git submodule status
```

> The submodules are pinned to committed revisions, so a plain
> `git submodule update --init` always reproduces the tested combination.

## Repository Layout

```text
RP1_firmware/
├── EtherCANFD/          # HPM USB-CANFD bridge firmware + host tools
├── roboparty_build/     # BSP build system (kernel / device tree / image)
└── roboparty_repo/       # APT manifest + Debian package sources
```

## Build From Here

| Your starting point | Where to go |
| :--- | :--- |
| **Build the board image** | [roboparty_build](https://github.com/Roboparty/roboparty_build) |
| **Build / flash the CAN bridge** | [EtherCANFD](https://github.com/Roboparty/roboparty_EtherCANFD) |
| **Package and publish the SDK** | [roboparty_repo](https://github.com/Roboparty/roboparty_repo) |
| **Deploy on the robot** | [RP1_deploy](https://github.com/Roboparty/RP1_deploy) |
| **Understand the platform** | [Documentation & know-how](https://roboparty.com/docs) |

## License

GPL-3.0, see [LICENSE](LICENSE). Each submodule is covered by its own license;
refer to the corresponding repository for details.

---

<p align="center">
  <strong>RoboParty</strong><br>
  Open hardware. Open intelligence. Shared possibility.
</p>
