<p align="center">
  <img src="assets/icon.png" width="128" alt="Conversio icon">
</p>

<h1 align="center">Conversio</h1>

<p align="center">Windows games from Steam on your Mac · by <a href="https://github.com/theoron-apps">Theoron</a></p>

<p align="center">
  <a href="../../releases/latest"><img src="https://img.shields.io/github/v/release/theoron-apps/Conversio?include_prereleases&style=flat-square&label=version&color=128AD8" alt="version"></a>
  <a href="../../releases"><img src="https://img.shields.io/github/downloads/theoron-apps/Conversio/total?style=flat-square&label=downloads&color=30D158&logo=github&logoColor=white" alt="downloads"></a>
  <img src="https://img.shields.io/badge/macOS-15%2B-1C1C1E?style=flat-square&logo=apple&logoColor=white" alt="macOS 15+">
  <img src="https://img.shields.io/badge/Apple%20silicon-M1%2B-1C1C1E?style=flat-square" alt="Apple silicon">
  <a href="https://t.me/TheoronApps"><img src="https://img.shields.io/badge/news-@TheoronApps-26A5E4?style=flat-square&logo=telegram&logoColor=white" alt="Telegram"></a>
</p>

<p align="center">
  <a href="../../releases/latest"><b>Download</b></a> ·
  English · <a href="README.ru.md">Русский</a> · <a href="README.uk.md">Українська</a>
</p>

<p align="center">
  <img src="assets/hero-en.jpg" width="900" alt="The Conversio game library on a MacBook">
</p>

---

Conversio runs the Windows version of Steam and your Windows games on a Mac with Apple silicon — like CrossOver, but **free**. It sets everything up in one click, keeps your games in a library with Steam artwork, and lets you tune every game separately.

## Features

<p align="center">
  <img src="assets/features-en.jpg" width="900" alt="Conversio features">
</p>

- **One-click setup** — Rosetta 2, Wine, DXVK and Steam for Windows, downloaded and installed for you.
- **Your Steam library** — installed games show up by themselves, with covers from Steam, search and a list of recently played games. Double-click to play.
- **Settings for every game** — D3DMetal or DXVK, MSync, Metal HUD with FPS, MetalFX upscaling, an FPS limit, launch arguments and environment variables.
- **Bottles** — separate Windows installations, each with its own drive C:, registry and settings, like in CrossOver. Run any `.exe`, `.msi` or `.bat`, add your own programs to the library, open Wine settings, the registry or the task manager.
- **Automatic graphics** — Conversio picks D3DMetal or DXVK by itself (32-bit DirectX 11 games go to DXVK). If a game fails to start, it retries with the other one and remembers what worked.
- **Game profiles** — known games set themselves up the first time they appear: GTA V Enhanced and Legacy, Euro Truck Simulator 2, American Truck Simulator, Hearts of Iron IV and Dota 2.
- **Rockstar Games Launcher** — GTA V starts through Steam and the Rockstar launcher, with sign-in, just like on Windows.
- **Low latency** — for DXVK games one frame in flight and no VSync; an FPS limit for any game; fullscreen that bypasses the macOS compositor.
- **Looks after your game** — warns when screen recording or low memory slows a game down, keeps the Mac awake while you play or download, and shows running games and downloads in the menu bar.
- **DirectX 12** — import D3DMetal from Apple's free Game Porting Toolkit, and DirectX 11 and 12 games run on Metal.
- **What's New** after every update, and automatic update checks.
- English, Ukrainian and Russian.

## How it works

Windows games don't run on macOS by themselves. Conversio puts three free layers in between:

| Layer | What it does | Where it comes from |
|---|---|---|
| **Wine** | Runs Windows programs: translates Windows calls into macOS ones | Our own builds of CrossOver's open-source Wine: [conversio-wine](https://github.com/theoron-apps/conversio-wine) |
| **DXVK** | Translates DirectX 9–11 into Vulkan, and MoltenVK turns it into Metal | [DXVK-macOS](https://github.com/Gcenx/DXVK-macOS) |
| **D3DMetal** *(optional)* | Apple's own translation of DirectX 11 and 12 into Metal | Apple's free [Game Porting Toolkit](https://developer.apple.com/games/game-porting-toolkit/) |
| **Rosetta 2** | Runs Intel code on Apple silicon | Built into macOS |

Nothing has to be bought. Wine and DXVK are downloaded automatically. D3DMetal is free too, but Apple doesn't allow other apps to ship it, so you download it yourself with a regular Apple ID (see below).

## Guides

Step by step, in English and Russian: [install](docs/guides/install.md) · [D3DMetal for DirectX 12](docs/guides/d3dmetal.md) · [GTA V Enhanced](docs/guides/gta-v-enhanced.md) · [troubleshooting](docs/guides/troubleshooting.md).

## Requirements

- A Mac with Apple silicon (M1 or later)
- macOS 15 Sequoia or later
- About 2 GB of free space for the engine and Steam, plus room for your games
- Liquid Glass buttons need macOS 26; on macOS 15 they use a blur instead

## Install

1. Download `Conversio-<version>.dmg` from [Releases](../../releases/latest).
2. Open the DMG and drag **Conversio** into **Applications**.
3. Open Conversio. macOS will say it can't verify the developer — click **Done**.
4. Open **System Settings → Privacy & Security** and scroll down to **Security**.
5. Click **Open Anyway** next to the Conversio message and confirm with your password or Touch ID.
6. Launch Conversio again — from now on it opens normally.

Why: the app isn't signed with a paid Apple Developer ID yet, so macOS asks you to confirm the first launch once.

> Advanced: instead of steps 3–5 you can run
> `xattr -dr com.apple.quarantine /Applications/Conversio.app`

## First launch

1. Click **Install Everything**. Conversio installs Rosetta 2 (macOS asks for your password), downloads Wine (about 300 MB) and DXVK, creates a bottle and installs Steam into it.
2. Steam opens. Sign in with your account.
3. Install a game in Steam as usual — after it finishes downloading, it appears in the Conversio library.
4. Hover over the cover and click **Play**.

## Playing games

Every game can start in one of two ways — pick it in **Game Settings** (right-click a cover):

| Launch mode | How it works | When to use |
|---|---|---|
| **Through Steam** *(default)* | Conversio asks Steam to start the game, just like on Windows | Most games, especially ones with launchers or DRM |
| **Directly** | Steam stays in the background, Conversio starts the game's `.exe` itself | When you want game settings to apply without restarting Steam |

Games started through Steam inherit Steam's settings. If a game has its own graphics settings and Steam is already running with different ones, Conversio offers to restart Steam.

### Game settings

| Setting | What it does |
|---|---|
| Graphics | **D3DMetal** (when imported) for DirectX 11/12, **DXVK** for DirectX 9–11, or the bottle's default |
| MetalFX | Apple's upscaling for games that support DLSS — D3DMetal only |
| DXVK async shaders | Less stutter while shaders compile |
| Synchronization | **MSync** (usually the fastest) or off |
| Metal HUD | FPS, frame time and GPU over the game |
| Launch arguments | For example `-dx11` or `-windowed` |
| Environment variables | `KEY=value`, one per line |

## DirectX 12 with D3DMetal

1. Open [developer.apple.com/games/game-porting-toolkit](https://developer.apple.com/games/game-porting-toolkit/) and sign in with your Apple ID (a free account is enough).
2. Download **Game Porting Toolkit**.
3. In Conversio, open **Settings → Engine** and click **Choose DMG…** next to D3DMetal. Pick the downloaded DMG — Conversio mounts it, copies D3DMetal into its Wine and unmounts it.

For DirectX 12 games such as GTA V Enhanced, use Game Porting Toolkit **4.0 beta 3 or later** — older versions lack what these games need.

After that, **D3DMetal** becomes the default graphics for all bottles. You can remove it at any time in the same place.

## Bottles

A bottle is a separate Windows: its own drive C:, registry, installed programs and settings. One bottle with Steam is enough for most people. Make another one (**File → New Bottle…**) when a game needs a different Windows version or settings that break other games.

On the bottle page you can open Steam, run any Windows installer or program, add a program to the library, open drive C: in Finder, open Wine settings, the registry or the task manager, and stop everything that runs in the bottle.

## Compatibility

Whether a game works depends on the game:

- **Usually work:** most DirectX 9–12 single-player games and many indie games.
- **Often don't work:** games with kernel-level anti-cheat (some EasyAntiCheat, BattlEye, Vanguard, Ricochet setups), and games that need AVX2 instructions Rosetta 2 can't translate on older macOS versions.
- If a game doesn't start, try the other graphics (D3DMetal ↔ DXVK), turn off MSync, or switch the launch mode. Turn on **Settings → General → Detailed Wine logs** and look at **Help → Wine Logs**.

### Tested games

Checked on a MacBook Pro with M5 Pro, macOS 26:

| Game | Status | Notes |
|---|---|---|
| GTA V Enhanced | ✅ Works | D3DMetal from Game Porting Toolkit 4.0 beta 3, story mode (online needs BattlEye, which doesn't run) |
| GTA V Legacy | ✅ Works | Story mode, borderless window |
| Euro Truck Simulator 2 | ✅ Works | D3DMetal |
| The Stanley Parable: Ultra Deluxe | ✅ Works | D3DMetal |
| R.E.P.O. | ✅ Works | D3DMetal |
| Age of History 3 | ✅ Works | |
| Dota 2 | ✅ Works | Audio set up by the game profile |
| Not For Broadcast | ✅ Works | Use the borderless window: exclusive fullscreen is cropped |
| City Car Driving | ✅ Works | 32-bit, DXVK is chosen automatically |
| Hearts of Iron IV | ⚠️ Works without the launcher | The Paradox Launcher stays blank, so Conversio starts the game directly |

Found a game that works or doesn't? [Open a game report](../../issues/new/choose) — it helps everyone.

## Update

Conversio checks for a new version when it launches and once a day. When one is out, it offers to **Download** it, remind you **Later** or **Skip** that version. Open the new DMG and replace the app in Applications — your bottles, games and settings are kept, and Conversio shows what's new.

You can turn the checks off or check manually in **Settings → About → Updates**. The engine is updated separately in **Settings → Engine**.

## Privacy

- Conversio collects no analytics.
- Network access is limited to downloading the engine from GitHub, the Steam installer and game covers from Valve's servers, and the update check against this GitHub repository, which sends nothing about you.
- Your Steam account is only ever entered into Steam itself.

## Where things are

| What | Where |
|---|---|
| Engine (Wine, DXVK, D3DMetal) | `~/Library/Application Support/Conversio/Engine` |
| Bottles with games and saves | `~/Library/Application Support/Conversio/Bottles` |
| Logs | `~/Library/Logs/Conversio` |
| Covers | `~/Library/Caches/Conversio` |

## Uninstall

Quit Conversio, delete it from Applications and, if you want to remove games and saves too, delete `~/Library/Application Support/Conversio`.

## License

Conversio is free to download and use. The app's source code is not public; the Wine builds it uses are open source under the LGPL in [conversio-wine](https://github.com/theoron-apps/conversio-wine). © 2026 Theoron.

## Acknowledgements

Conversio stands on the shoulders of [Wine](https://www.winehq.org) (LGPL), [DXVK](https://github.com/doitsujin/dxvk) (zlib), [MoltenVK](https://github.com/KhronosGroup/MoltenVK) (Apache 2.0), the macOS builds by [Gcenx](https://github.com/Gcenx), and Apple's Game Porting Toolkit. Steam is a trademark of Valve Corporation. Conversio is not affiliated with Valve, Apple, Microsoft or CodeWeavers. The games on the screenshots are made up.

## Support

Conversio is free. If it helped you, you can [support development](https://send.monobank.ua/jar/2jGp4yDQPd) with any Visa or Mastercard, Apple Pay or Google Pay.

## Contact

News and support — Telegram [@TheoronApps](https://t.me/TheoronApps) or email [theoronapps@gmail.com](mailto:theoronapps@gmail.com).
