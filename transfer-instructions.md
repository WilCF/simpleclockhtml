# Getting the clock to your iPad 2

You have two files: `clock.html` and `clock.appcache` — keep them in the same folder.

---

## Step 1: Serve the files from your Mac

Open Terminal and run:

```bash
cd /path/to/folder/containing/clock/files
python3 -m http.server 8000
```

Leave Terminal open. You should see: `Serving HTTP on 0.0.0.0 port 8000`

---

## Step 2: Connect iPad via USB and share internet

1. Plug iPad into your Mac with a Lightning/30-pin cable
2. Open **System Settings → General → Sharing** (or System Preferences → Sharing on older macOS)
3. Enable **Internet Sharing**
   - Share your connection from: **Wi-Fi** (or Ethernet — whatever your Mac uses for internet)
   - To computers using: **iPhone USB** (it will appear when iPad is plugged in)
4. Turn Internet Sharing **On**

Your Mac will now act as a router for the iPad over USB.

---

## Step 3: Find your Mac's USB IP address

In Terminal, run:

```bash
ifconfig bridge100 | grep inet
```

You'll see something like `inet 192.168.2.1` — that's your Mac's address on the USB bridge.

---

## Step 4: Load the page on the iPad

On the iPad, open **Safari** and go to:

```
http://192.168.2.1:8000/clock.html
```

The clock should appear. Wait a few seconds for the appcache to finish loading (Safari will silently cache the page for offline use).

---

## Step 5: Save to home screen (optional but recommended)

Once loaded:
1. Tap the **Share** button (box with arrow) in Safari
2. Tap **Add to Home Screen**
3. Name it "Clock" and tap Add

This creates a full-screen app icon. When launched from the home screen, it runs full-screen with no Safari chrome, and works completely **offline** — no Wi-Fi needed.

---

## After setup

Once cached, the iPad never needs to connect again. You can:
- Disconnect the USB cable
- Turn off Internet Sharing on your Mac
- Launch the clock from the home screen icon any time

The appcache stores the page permanently in Safari's cache on the device.
