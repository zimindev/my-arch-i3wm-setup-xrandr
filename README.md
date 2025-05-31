## ✅ Step-by-Step Guide: xrandr Setup with Autostart in i3wm

---

### 1. ✅ **Install `xrandr`**

Open a terminal and run:

```bash
sudo pacman -S xorg-xrandr
```

---

### 2. ✅ **Create Your Monitor Setup Script**

Let’s create a shell script with your configuration. Save it as `monitors.sh` in your home directory, e.g. `~/.config/monitors.sh`.

```bash
mkdir -p ~/.config

nano ~/.config/monitors.sh
```

Paste the following content:

```sh
#!/bin/sh

# Multi-monitor layout
xrandr \
  --output DVI-D-0 --primary --mode 2560x1080 --pos 1080x1080 --rotate normal \
  --output HDMI-0 --mode 2560x1080 --pos 3640x0 --rotate right \
  --output DP-0 --off \
  --output DP-1 --mode 2560x1080 --pos 1080x0 --rotate normal \
  --output DP-2 --mode 2560x1080 --pos 0x0 --rotate left \
  --output DP-3 --off \
  --output DP-4 --off \
  --output DP-5 --off
```

Save and exit (`Ctrl + O`, `Enter`, then `Ctrl + X`).

Then make the script executable:

```bash
chmod +x ~/.config/monitors.sh
```

---

### 3. ✅ **Autostart Script in i3**

Edit your i3 config file, usually located at:

```bash
~/.config/i3/config
```

Add the following line **at the top** (or after other `exec` commands):

```bash
exec --no-startup-id ~/.config/monitors.sh
```

> ✅ `--no-startup-id` keeps the i3 bar clean (no unnecessary icons or notifications).

---

### 4. 🔄 **Apply Without Reboot**

You can apply the script manually to test it without restarting:

```bash
~/.config/monitors.sh
```

Or restart i3 with:

```bash
Mod + Shift + R
```

---

## ✅ Done!
