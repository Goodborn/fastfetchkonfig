# Fastfetch Config

A clean, categorized fastfetch config with a box-drawn layout.

![screenshot](screenshot.png)

## Preview

```
┌──────────── Hardware ────────────┐
│  󰒅     B650 AORUS ELITE AX
│  󰍛     AMD Ryzen 7 7800X3D
│  󰓅     32 GB
│  󰾲     NVIDIA GeForce RTX 3060 Ti
│  󰋊     ████████░░ 450G / 1T
└──────────────────────────────────┘

┌──────────── Software ────────────┐
│  󰣇     CachyOS
│  󰓛     6.12.4-1-cachyos
│  󰢮     550.127.05
└──────────────────────────────────┘

┌───────── Miscellaneous ──────────┐
│  󱫐     3 hours 42 minutes
│  󰥔     Day 12
└──────────────────────────────────┘
```

## Install

```bash
cp config.jsonc ~/.config/fastfetch/config.jsonc
cp -r images/ ~/.config/fastfetch/images/
cp -r ascii/ ~/.config/fastfetch/ascii/
```

## Customization

- **Logo**: Replace `~/.config/fastfetch/images/cachy.png` with your distro logo, or change the path in `config.jsonc`. ASCII art alternatives are in `ascii/`.
- **Secondary disks**: Add mount points to the `folders` field in the Hardware disk module (e.g. `"/:/mnt/Data"`).
- **GPU driver**: The driver command uses `glxinfo` which works for most GPUs. For NVIDIA-only, replace with `nvidia-smi --query-gpu=driver_version --format=csv,noheader`.

## Requirements

- [fastfetch](https://github.com/fastfetch-cli/fastfetch)
- A [Nerd Font](https://www.nerdfonts.com/) for the icons
- Kitty, Alacritty, or another terminal that supports image rendering (for PNG logos)
