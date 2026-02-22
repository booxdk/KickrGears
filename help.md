# KICKR Gears - Help & Documentation

Complete guide for using KICKR Gears with your WAHOO KICKR bike.

## Table of Contents

- [Getting Started](#getting-started)
- [Understanding the Display](#understanding-the-display)
- [Using with Zwift](#using-with-zwift)
- [Customization](#customization)
- [Troubleshooting](#troubleshooting)
- [Keyboard Shortcuts](#keyboard-shortcuts)
- [Technical Details](#technical-details)
- [Privacy & Permissions](#privacy--permissions)

---

## Getting Started

### First Launch

1. **Power on** your KICKR bike
2. **Launch** KICKR Gears
3. The app will **automatically scan** for your KICKR
4. Once connected, you'll see your current gears displayed

### Initial Setup

The app will automatically:
- Scan for nearby KICKR devices
- Connect to your bike via Bluetooth
- Start displaying gear data in real-time

No configuration needed!

---

## Understanding the Display

### Front Gears (Top Row)

**Number Display:**
- Shows current front chainring: 1, 2, or 3

**Visual Indicators:**
- Three vertical bars representing your chainrings
- Bars increase in height (small → medium → large)
- White highlight = currently selected gear
- Gray = available but not selected

### Rear Gears (Bottom Row)

**Number Display:**
- Shows current rear cog: 01 through 13
- Zero-padded (e.g., "04" not "4")

**Visual Indicators:**
- Thirteen vertical bars representing your cassette
- Heights are inverted: Gear 1 = tallest, Gear 13 = shortest
  - This matches reality: larger cogs = easier gears
- White highlight = currently selected gear
- Gray = available but not selected

---

## Using with Zwift

### Setup for Best Results

1. **Launch Zwift FIRST**
2. **Use windowed mode** (not fullscreen)
   - Zwift → Settings → Display → Windowed mode
3. **Launch KICKR Gears**
4. **Position the window**:
   - Right-click → "Unlock Position"
   - Drag to desired location (bottom corner recommended)
   - Right-click → "Lock Position"

### Why Windowed Mode?

Fullscreen mode prevents other windows from showing on top. Zwift in windowed mode allows KICKR Gears to float over the game.

### Recommended Positioning

- **Bottom left or right corner** - doesn't block important game UI
- **Near your power/cadence display** - keep all data together
- **Above the minimap** - easy to glance at

---

## Customization

### Accessing Settings

- **Menu bar**: KickrGears → Settings (⌘,)
- **Right-click**: Settings...

### Appearance Settings

**Scale (60% - 160%)**
- Makes the entire HUD larger or smaller
- Useful for different screen sizes or viewing distances
- Scales everything proportionally (numbers, bars, window)

**Transparency (0% - 100%)**
- 0% = Fully transparent (invisible background)
- 100% = Solid black background
- Recommended: 60-80% for good visibility without blocking too much

### Window Settings

**Enable Dragging**
- Unlock: Drag window freely
- Lock: Window stays in place (recommended while riding)

**Reset Position**
- Centers window on your main screen
- Useful if window gets lost off-screen

---

## Troubleshooting

### "No KICKR found"

**Possible causes:**
- KICKR is not powered on
- Another app is connected to the KICKR (Zwift, Wahoo Fitness, etc.)
- Bluetooth is disabled on your Mac

**Solutions:**
1. Check KICKR is powered on and within range
2. Close other apps that might be using the KICKR
3. Click "Retry" to scan again
4. Restart the app if needed

### Gears Not Updating

**If gears are stuck or not changing:**
1. Check connection status in Settings
2. Try disconnecting and reconnecting
3. Shift gears on your bike to test
4. Restart KICKR Gears

### Random Gear Numbers

**If you see crazy numbers like "91" or "228":**
- This is caused by touching brake levers
- The app filters most of these out automatically
- They should disappear within 1 second
- This is a known KICKR behavior, not a bug

### Window Keeps Moving

**If window moves when you don't want it to:**
- Right-click → "Lock Position"
- Check Settings → Window → "Enable Dragging" is OFF

### Display Too Small/Large

**Adjust the size:**
- Settings → Appearance → Scale slider
- Or use the transparency slider if background is too dark

---

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| ⌘, | Open Settings |
| ⌘? | Open Help Guide |
| ⌘Q | Quit app |

### Context Menu (Right-click)

- Lock/Unlock Position
- Settings...
- Quit

---

## Technical Details

### Bluetooth Connection

**Service UUID:** `A026EE0D-0A7D-4AB3-97FA-F1500F9FEB8B`
**Characteristic UUID:** `A026E03A-0A7D-4AB3-97FA-F1500F9FEB8B`

KICKR Gears connects using the same Bluetooth protocol as the Arduino-based KICKR gear displays.

### Data Format

Gear data is read from bytes 2 and 3 of the characteristic:
- Byte 2: Front gear (0-2, displayed as 1-3)
- Byte 3: Rear gear (0-12, displayed as 1-13)

### Data Validation

The app validates incoming data to ensure:
- Front gear is between 1-3
- Rear gear is between 1-13
- Invalid data (from brake levers) is filtered out

### System Requirements

- **macOS Version:** 13.0 (Ventura) or later
- **Bluetooth:** Required and enabled
- **Compatible Devices:** WAHOO KICKR bikes with electronic shifting
- **RAM:** Minimal (< 50 MB)
- **CPU:** Negligible impact

### Architecture

- **Language:** Swift 5.0
- **Framework:** SwiftUI
- **Bluetooth:** Core Bluetooth
- **Storage:** UserDefaults for preferences
- **Window Management:** AppKit

---

## Privacy & Permissions

### Required Permissions

**Bluetooth Access:**
- Required to connect to your KICKR bike
- Requested on first launch
- Can be managed in System Settings → Privacy & Security → Bluetooth

### Data Privacy

KICKR Gears:
- ✅ Does NOT collect any data
- ✅ Does NOT require internet connection
- ✅ Does NOT send data anywhere
- ✅ Stores only local preferences (window position, scale, etc.)
- ✅ No analytics, no tracking, no telemetry

All data stays on your Mac.

---

## Tips & Best Practices

### Performance

- **Minimal impact**: Uses less than 1% CPU when idle
- **Battery friendly**: Negligible battery drain on MacBooks
- **Always-on-top**: Window stays visible over all apps

### Workflow Tips

1. **Set up once**: Position and lock the window where you want it
2. **Launch order**: Zwift first, then KICKR Gears
3. **Check connection**: Make sure "Connected" shows in Settings before riding
4. **Adjust transparency**: Lower if Zwift content makes numbers hard to read

### Multi-Monitor Setup

- Window remembers position on the monitor it was last on
- Works across spaces/desktops
- Stays on top of fullscreen apps (if app is windowed)

---

## Support & Feedback

### Getting Help

- Check this help guide first
- Look through [GitHub Issues](https://github.com/booxdk/KickrGears/issues)
- Open a new issue if you find a bug

### Feature Requests

Have an idea? Open an issue with the "enhancement" label.

### Supporting Development

If you find KICKR Gears useful:

**[Buy me a coffee](https://buymeacoffee.com/booxdk)** ☕

Your support helps keep this project maintained!

---

**Version:** 1.0  
**Last Updated:** February 2026  
**Made with ❤️ for cyclists**
