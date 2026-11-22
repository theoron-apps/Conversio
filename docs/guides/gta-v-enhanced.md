# GTA V Enhanced

| | |
|---|---|
| Story mode | ✅ Works |
| GTA Online | ❌ Doesn't work on a Mac, neither in Conversio nor in CrossOver: the BattlEye anti-cheat blocks Wine |
| Graphics | DirectX 12 only → needs **D3DMetal** |
| Recommended Mac | M1 Pro or later, 16 GB of memory or more, macOS 26 |

## Before you start

1. Install Conversio with the [install guide](install.md).
2. Import D3DMetal with the [D3DMetal guide](d3dmetal.md) — the game won't start without it.
3. Install **Grand Theft Auto V Enhanced** in Steam inside Conversio.

When the game shows up in the library, Conversio applies its profile by itself: D3DMetal, MSync and low latency. You can see it in **Game Settings** (right-click the cover) — the "Conversio profile" block at the top.

## First launch

1. Click **Play**. The **Rockstar Games Launcher** starts first — on the first run it finishes installing itself, which can take a couple of minutes.
2. Sign in to your Rockstar account in the launcher.
3. Choose **Story Mode** in the game menu.

## Settings for the most FPS

In the game, **Settings → Graphics**:

- **Screen type:** fullscreen. Keep **Capture the display in fullscreen** on in the bottle (it is by default) — it lowers latency.
- **Upscaling: DLSS → Quality or Balanced.** D3DMetal swaps DLSS for Apple's MetalFX — the biggest FPS gain.
- **Ray tracing:** off — it costs the most on a Mac.
- **VSync:** off if low latency matters to you.

In Conversio:

- **Retina mode** in the bottle — off (the default). Turn it on only if you have FPS to spare.
- **Metal HUD** in game settings shows FPS and frame time — handy for comparing settings.

## If the game doesn't start

- **`ERR_GFX_D3D_NOD3D12`** — D3DMetal isn't imported or isn't selected. Check **Settings → Engine** and the graphics in game settings.
- **The Rockstar launcher hangs while loading** — click **Stop Everything** on the bottle page and start again.
- **It stopped working after a game update** — that happens: GTA updates sometimes break compatibility. Let us know in a [game report](https://github.com/theoron-apps/Conversio/issues/new/choose).
