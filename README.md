#!/bin/sh

# Original multi-monitor layout with various positions and rotations
xrandr \
  --output DVI-D-0 --primary --mode 2560x1080 --pos 1080x1080 --rotate normal \
  --output HDMI-0 --mode 2560x1080 --pos 3640x0 --rotate right \
  --output DP-0 --off \
  --output DP-1 --mode 2560x1080 --pos 1080x0 --rotate normal \
  --output DP-2 --mode 2560x1080 --pos 0x0 --rotate left \
  --output DP-3 --off \
  --output DP-4 --off \
  --output DP-5 --off

# Alternative cleaner layout (optional, uncomment to use)
# xrandr \
#   --output DVI-D-0 --mode 2560x1080 --pos 0x0 --rotate normal \
#   --output HDMI-0 --mode 2560x1080 --pos 2560x0 --rotate right \
#   --output DP-1 --mode 2560x1080 --pos 5120x0 --rotate normal \
#   --output DP-2 --mode 2560x1080 --pos 7680x0 --rotate left
