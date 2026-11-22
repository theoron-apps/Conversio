# D3DMetal for DirectX 12 games

D3DMetal is Apple's own translation of DirectX 11 and 12 into Metal. It's free, but Apple doesn't allow other apps to ship it, so you download it yourself, once.

## 1. Download "Evaluation environment for Windows games"

1. Open [Apple's downloads page](https://developer.apple.com/download/all/?q=game%20porting%20toolkit) and sign in with your Apple ID. A regular free account works; you don't need to **Enroll** in the paid program.
2. Find **Evaluation environment for Windows games** — that's the one with D3DMetal. The plain "Game Porting Toolkit" is developer tools; you don't need it.
3. Take the newest version — **4.0 beta 3 or later**. DirectX 12 games such as GTA V Enhanced need it; older games run on it too. Version 3.0 also works for most DirectX 11 games.
4. Click **View Details** and download the `.dmg` into Downloads.

> If Apple's site keeps loading forever, open it in another browser or a private window and turn off your ad blocker.

## 2. Import it into Conversio

Conversio finds the image in Downloads, or a disk that's already mounted:

1. The welcome screen (or **Settings → Engine**) shows "**Found: Evaluation_environment_for_Windows_games_<version>.dmg**".
2. Click **Import**.
3. If **Apple's license agreement** opens, read it and click **Agree**. Conversio never accepts the license for you.
4. Done: D3DMetal is copied and the image is unmounted. Game settings now offer **D3DMetal** graphics.

You can import before Wine is installed — D3DMetal waits and moves into Wine automatically.

## If it doesn't work

- **"The selected file doesn't contain D3DMetal"** — that's the wrong DMG (for example, "Game Porting Toolkit" instead of "Evaluation environment").
- **"The image never got mounted"** — double-click the DMG, click **Agree**, then click **Import** in Conversio again: it will see the mounted disk.
- **Remove D3DMetal** — **Settings → Engine → Remove D3DMetal**.
