# Used Laptop Testing ISO

An unofficial customized SystemRescue 13.02 image for inspecting and testing used laptops.

The ISO includes:

- OpenCode 1.18.29 at `/usr/local/bin/opencode`
- a clean, no-login OpenCode configuration using `opencode/big-pickle`
- full OpenCode tool access enabled by default
- a laptop-testing prompt at `/root/systemrescue_opencode full test.md`
- an XFCE desktop launcher for OpenCode
- no copied account credentials, API keys, sessions, caches, or history

## Download

Download the ISO and `SHA256SUMS` from the latest GitHub Release. This repository intentionally does not commit the ISO as a Git object.

Verify the download with:

```bash
sha256sum --check SHA256SUMS
```

The expected ISO SHA-256 is:

```text
0aae848951359c8cd9602b0253c044cdddcc02a4334ffd79b44078b2ce43b574
```

The ISO is intended to be selected directly from a Ventoy boot menu.

## Validation

The customized image was tested through real QEMU boots. Validation covered SystemRescue startup, prompt integrity, offline OpenCode startup, anonymous Big Pickle inference, shell and file tool use, subagent execution, Exa web search, the XFCE desktop launcher, and a second clean boot with no persisted OpenCode state.

## Upstream projects and source

This is an unofficial community customization. It is not affiliated with or endorsed by the SystemRescue or OpenCode projects.

- SystemRescue website: https://www.system-rescue.org/
- SystemRescue 13.02 source: https://gitlab.com/systemrescue/systemrescue-sources/-/tree/13.02
- SystemRescue customization documentation: https://www.system-rescue.org/scripts/sysrescue-customize/
- OpenCode website: https://opencode.ai/
- OpenCode 1.18.29 source: https://github.com/anomalyco/opencode/tree/v1.18.29

SystemRescue sources are licensed under GPLv3. Programs included by SystemRescue retain their respective licenses and notices. OpenCode is distributed under the MIT License. See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

The hosted anonymous model is an external service and its availability may change. No model credentials are embedded in the ISO.
