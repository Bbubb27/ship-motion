# Ship motion — live

The phone streams its motion sensors through a free public relay, and the Mac shows the live model. Both devices only need internet; they never talk to each other directly, so ship Wi-Fi blocking doesn't matter.

- `sensor.html`: open on the **phone**
- `index.html`: the live display, open on the **Mac**

## 1. Put it on GitHub Pages (once, ~3 minutes)

1. On github.com: **New repository** → name it `ship-motion` → **Public** → Create.
2. On the new repo page: **Add file → Upload files**, drag in **all** the files from this folder, then **Commit changes**.
3. **Settings → Pages** → under *Build and deployment*, Source: **Deploy from a branch**, Branch: **main**, folder **/ (root)** → **Save**.
4. Wait a minute or two. Your site is `https://YOUR-USERNAME.github.io/ship-motion/`.

## 2. Run it

**Phone (Safari):**
1. Go to `https://YOUR-USERNAME.github.io/ship-motion/sensor.html`.
2. Put the phone flat on the floor: screen up, charging port toward the bow.
3. Tap **Start** → **Allow** motion access. Note the 4-digit room code.
4. Check "Phone flat" says Yes. Leave the page open and the screen on. If "Screen kept on" isn't Yes, set Settings → Display & Brightness → Auto-Lock → Never for now.

**Mac:**
1. Go to `https://YOUR-USERNAME.github.io/ship-motion/`.
2. Type the room code → **Connect**. The status turns green and says "Live" within a few seconds.
3. The ship motion settles after ~30 s; the sea appears after 40 s.

**Demo replay** on the Mac page replays the 25 Nov recording, so you can check the page works before setting up the phone.

## Notes
- Data goes through public test relays (HiveMQ, EMQX, Mosquitto) under a random room code. It's only phone motion numbers, but anyone who guessed the code could see them.
- The page sends to all three relays at once, so it keeps working if one is down.
- Uses about 3–4 KB/s of internet on each device (~13 MB per hour).
- Speed and wave direction are set in the display page; the cabin TV's navigation channel is the best source.
