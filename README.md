# iPad 2 Clock

A dead-simple fullscreen digital clock for iPad 2 (iOS 9.3.5). No dependencies, no external resources, works offline via appcache.

## Files

- `clock.html` — the clock page
- `clock.appcache` — offline cache manifest (must be in the same directory)

## Loading on the iPad

### Option 1: GitHub Raw (easiest)

On the iPad, open Safari and go to the raw URL for `clock.html`:

```
https://raw.githubusercontent.com/YOUR_USERNAME/YOUR_REPO/main/clock.html
```

Wait for it to fully load. The appcache will cache it for offline use.

### Option 2: Local server

```bash
python3 -m http.server 8000
```

Then navigate to `http://YOUR_MAC_IP:8000/clock.html` on the iPad.

## Add to Home Screen

Once loaded in Safari:

1. Tap the Share button
2. Tap **Add to Home Screen**
3. Tap Add

Launches full-screen with no browser chrome. Works offline after first load.

## Compatibility

- iOS 9.3.5 / Safari WebKit ~601
- ES5 only, no external fonts or scripts
- Handles portrait and landscape rotation
