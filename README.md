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

## Customize

All editable values are in `config.jsonc`. Everything else is auto-detected.

| What | Line | Default | Change to |
|------|------|---------|-----------|
| Logo image | `3` | `~/.config/fastfetch/images/cachy.png` | Your logo path |
| RAM display | `59` | `{ram-total} GB` | `{ram-used} GB / {ram-total} GB` |
| GPU display | `65` | `{gpu-name}` | `{gpu-vendor} {gpu-name}` |
| Disks shown | `74` | `"/"` | `"/:/mnt/Data:/mnt/Backup"` |
| GPU driver | `103` | `glxinfo ...` | `nvidia-smi ...` for NVIDIA |

```jsonc
// Logo — point to your distro image or an ASCII art file
"source": "~/.config/fastfetch/images/cachy.png"

// RAM — swap between total, used, or percentage
"format": "{ram-total} GB"

// GPU — auto-detected, no need to hardcode
"format": "{gpu-name}"

// Disks — colon-separated list of mount points
"folders": "/:/mnt/Backup"

// GPU driver — glxinfo (all), nvidia-smi (NVIDIA), or remove the module entirely
"text": "glxinfo 2>/dev/null | grep 'OpenGL version' | sed 's/.*: //'"
```

Drop your logo PNG into `images/`, or swap the logo source to an ASCII art file from `ascii/`.

## Requirements

- [fastfetch](https://github.com/fastfetch-cli/fastfetch)
- A [Nerd Font](https://www.nerdfonts.com/) for the icons
- Kitty, Alacritty, or another terminal that supports image rendering (for PNG logos)
