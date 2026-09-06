# Used Laptop Testing ISO

Boot a used laptop, connect it to the internet, and run a structured hardware inspection without installing an operating system or using persistence.

This is an unofficial SystemRescue 13.02 image with OpenCode and a general used-laptop testing prompt built into the live environment. The prompt assesses the tested laptop on its capabilities, condition, Linux compatibility, and value.

## Download

[Download the current ISO from the latest release](https://github.com/ilyasmohaimel/used-laptop-testing-iso/releases/latest).

The ISO is distributed as a GitHub Release asset instead of being committed to the Git repository. The release contains the bootable image and its third-party notices. A separate checksum file is not included.

## What is included

- SystemRescue 13.02 for x86-64 systems
- OpenCode 1.18.29 at `/usr/local/bin/opencode`
- the default anonymous model `opencode/big-pickle`
- automatic OpenCode tool permission through `"permission": "allow"`
- the testing prompt at `/root/systemrescue_opencode full test.md`
- an XFCE desktop launcher at `/root/Desktop/OpenCode.desktop`
- no copied accounts, API keys, credentials, sessions, caches, or history

The prompt covers hardware identification, Linux compatibility, storage and battery health, thermal and error checks, a bounded CPU and memory sanity test, workload scoring, and a concise buying recommendation. Its storage rules prohibit mounting, modifying, repairing, formatting, or stress-testing internal drives.

## Use with Ventoy

1. Download `systemrescue-13.02-amd64-opencode.iso` from the latest release.
2. Copy the ISO to the data partition of an existing Ventoy USB. Do not extract it.
3. Boot the ISO from the Ventoy menu.
4. Connect Wi-Fi, USB tethering, or Ethernet.
5. Open **OpenCode** from the XFCE desktop, or run `opencode` in a terminal.
6. Open `/root/systemrescue_opencode full test.md` and give its contents to OpenCode when you are ready to start the inspection.

The launcher opens a clean OpenCode session in `/root`. It does not start the test automatically, giving you time to connect the network and review the machine first.

## Permissions and privacy

OpenCode runs as SystemRescue's root user with tool permission set to `allow`. This is intentional for automated hardware diagnostics, but it also means shell and file operations are not stopped by approval prompts. Review the included prompt's safety rules and supervise the test.

No OpenCode authentication file or host-machine configuration is embedded. When the ISO is booted without persistence, runtime conversations, caches, and temporary files disappear after shutdown.

Big Pickle is a hosted external model. Inference requires internet access, and anonymous availability can change independently of this ISO. The OpenCode executable and its version check work offline.

## Validation

The exact public v2 ISO was booted in QEMU and checked for:

- successful SystemRescue startup
- the generalized prompt and its expected embedded contents
- `opencode --version` reporting 1.18.29 offline
- valid full-access OpenCode configuration
- the XFCE desktop launcher
- absence of baked-in authentication state

Before the prompt-only generalized rebuild, the same OpenCode payload also passed live anonymous inference, shell and file tool use, subagent execution, Exa web search, desktop launcher, and clean-second-boot tests. Hardware coverage still depends on the laptop, firmware, and kernel support.

## Upstream projects and licensing

This customization is not affiliated with or endorsed by SystemRescue or OpenCode.

- [SystemRescue](https://www.system-rescue.org/)
- [SystemRescue 13.02 source](https://gitlab.com/systemrescue/systemrescue-sources/-/tree/13.02)
- [Official SystemRescue customization documentation](https://www.system-rescue.org/scripts/sysrescue-customize/)
- [OpenCode](https://opencode.ai/)
- [OpenCode 1.18.29 source](https://github.com/anomalyco/opencode/tree/v1.18.29)

SystemRescue sources are licensed under GPLv3. Programs included by SystemRescue retain their respective licenses and notices. OpenCode is distributed under the MIT License. See [Third-party notices](THIRD_PARTY_NOTICES.md).
