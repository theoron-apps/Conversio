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

When the game shows up in the library, Conversio applies its profile by itself: D3DMetal and DLSS through MetalFX. You can see it in **Game Settings** (right-click the cover) — the "Conversio profile" block at the top.

## First launch

1. Click **Play**. The **Rockstar Games Launcher** starts first — on the first run it finishes installing itself, which can take a couple of minutes.
2. Sign in to your Rockstar account in the launcher.
3. Choose **Story Mode** in the game menu.

## Tested settings

These are the settings Conversio's author plays with on a MacBook Pro with M5 Pro. In the game, **Settings → Graphics** (option names may differ slightly in your language):

**Video**

| Setting | Value |
|---|---|
| Screen type | Windowed borderless |
| Resolution | 1728 x 1117 |
| Refresh rate | 120Hz |
| Frame rate limit | Off |
| VSync | On |
| NVIDIA Reflex | On |
| Pause game on focus loss | Off |

**Ray tracing** — everything off: it costs the most on a Mac.

**Resolution scaling**

| Setting | Value |
|---|---|
| Resolution scaling method | AMD FSR 3 |
| AMD FSR 3 quality mode | Balanced |
| Frame generation | Off |
| Anti-aliasing | AMD FSR 3 (set by the game) |
| Sharpening | Maximum |

**Quality**

| Setting | Value |
|---|---|
| Shader quality | High |
| Texture quality | Very High |
| Anisotropic filtering | X8 |
| Particles quality | High |
| Tessellation | High |
| Water quality | High |
| Grass quality | High |

**Lighting**

| Setting | Value |
|---|---|
| Lighting quality | Standard |
| Reflection quality | High |
| Shadow quality | High |
| Soft shadows | Softer |
| Long shadows | Off |
| High resolution shadows | Off |

**Post FX**

| Setting | Value |
|---|---|
| Post FX | High |
| Depth of field | Off |
| Motion blur strength | Zero |
| Ambient occlusion | Off |

**Scene**

| Setting | Value |
|---|---|
| Population density | Maximum |
| Population variety | Maximum |
| Distance scaling | Maximum |
| High detail streaming while flying | On |
| Extended distance scaling | Maximum |

In Conversio:

- **Capture the display in fullscreen** in the bottle — on (the default): it lowers latency.
- **Retina mode** in the bottle — off (the default). Turn it on only if you have FPS to spare.
- **Metal HUD** in game settings shows FPS and frame time — handy for comparing settings.

## If the game doesn't start

- **`ERR_GFX_D3D_NOD3D12`** — D3DMetal isn't imported, isn't selected, or comes from Game Porting Toolkit 3.0: the game needs 4.0 or newer. Check **Settings → Engine** and the graphics in game settings.
- **The Rockstar launcher hangs while loading** — click **Stop Everything** on the bottle page and start again.
- **It stopped working after a game update** — that happens: GTA updates sometimes break compatibility. Let us know in a [game report](https://github.com/theoron-apps/Conversio/issues/new/choose).
