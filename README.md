# Fastfetch Config

A clean, categorized fastfetch config with a box-drawn layout.

<table>
  <tr>
    <td><b>CachyOS</b><br><img src="cachyospreview.png" width="400"></td>
    <td><b>Nobara</b><br><img src="nobarapreview.png" width="400"></td>
  </tr>
</table>

## Install

### Download only (~/Downloads)

```bash
git clone https://github.com/Goodborn/fastfetchkonfig.git ~/Downloads/fastfetch
```

### Download and install directly

> **Warning:** This will overwrite your existing `config.jsonc`. Back up your current config first if you want to keep it.

```bash
git clone https://github.com/Goodborn/fastfetchkonfig.git /tmp/fastfetch && cp /tmp/fastfetch/config.jsonc ~/.config/fastfetch/config.jsonc && cp -r /tmp/fastfetch/images/ ~/.config/fastfetch/images/ && cp -r /tmp/fastfetch/ascii/ ~/.config/fastfetch/ascii/ && rm -rf /tmp/fastfetch
```

## Customize

Edit `config.jsonc` to change these values:

```jsonc
"source": "~/.config/fastfetch/images/cachy.png"  // your logo
"format": "{ram-total} GB"                         // RAM display
"format": "{gpu-name}"                             // GPU display
"folders": "/"                                     // disks to show, e.g. "/:/mnt/HDD"
"text": "glxinfo 2>/dev/null | grep 'OpenGL version' | sed 's/.*: //'"  // GPU driver
```

Drop your logo PNG into `images/` or use an ASCII art file from `ascii/`. Find disk mount points with `lsblk` or `df -h`.

## Requirements

- [fastfetch](https://github.com/fastfetch-cli/fastfetch)
- A [Nerd Font](https://www.nerdfonts.com/) for the icons
- Kitty, Alacritty, or another terminal that supports image rendering (for PNG logos)
