# A game doesn't start or runs slowly

Go through the steps from the top — one of the first usually helps.

## Doesn't start

1. **Ask Conversio.** Right-click the game → **Why Won't It Start?…** Conversio shows which graphics actually loaded, the important lines of the game's, DXVK's and Wine's logs, and hints for known causes. **Copy Report** gives you text for Telegram or Issues.
2. **Try other graphics.** Game Settings → Graphics: "Automatic" switches D3DMetal ↔ DXVK by itself when a game closes right after starting. You can also pick one. DirectX 12 games need D3DMetal.
3. **Black screen with sound.** The game may have turned on HDR (XDR screens) — look for HDR in its settings. If the game has an OpenGL mode, try it (Euro Truck Simulator 2 and American Truck Simulator: `-rdevice gl -nointro`, which Conversio sets for you).
4. **Switch the launch mode.** "Through Steam" ↔ "Directly".
5. **Turn synchronization off.** Bottle page → Synchronization → Off. MSync sometimes upsets older games.
6. **Stop everything and start again.** Bottle page → **Stop Everything**.
7. **Detailed log.** Settings → General → **Detailed Wine logs**, start the game and open **Why Won't It Start?…** again.

## Runs slowly

- Is **Retina mode** off? (Bottle page.) It renders at the display's full resolution — 2 to 4 times more pixels.
- Turn on **DLSS** or **FSR** in the game — on D3DMetal, DLSS becomes MetalFX.
- Lower the in-game resolution and turn on upscaling.
- Set an **FPS limit** (DXVK) — a steady 60 beats a jumpy 50–80.
- A MacBook on battery is slower — plug in the charger.

## Input lag

- Play in **fullscreen** with **display capture** on in the bottle.
- Turn on **Low latency** in game settings (DXVK) and turn VSync off in the game.
- A wired mouse or one with its own 2.4 GHz receiver responds faster than Bluetooth.

## Still stuck

Open a [game report](https://github.com/theoron-apps/Conversio/issues/new/choose) and attach the log — that lets us add a profile for the game.
