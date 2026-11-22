# Install Conversio

Takes about 15 minutes, mostly downloads. You need a Mac with Apple silicon (M1 or later) and macOS 15 or later.

## 1. Download the app

1. Open the [latest release](https://github.com/theoron-apps/Conversio/releases/latest).
2. Under **Assets**, download `Conversio-<version>.dmg`.
3. Open the DMG and drag **Conversio** into **Applications**.

## 2. Allow the first launch

The app isn't signed with a paid Apple certificate yet, so macOS asks once:

1. Open Conversio. When macOS says it can't verify the developer, click **Done**.
2. Open **System Settings → Privacy & Security** and scroll down.
3. Next to the Conversio message, click **Open Anyway** and confirm with your password or Touch ID.

> Faster, in Terminal: `xattr -dr com.apple.quarantine /Applications/Conversio.app`

## 3. Install everything

1. On the welcome screen, click **Install Everything**.
2. macOS asks for your password to install Rosetta 2 — Apple's translator that Wine needs.
3. Conversio downloads Wine (~300 MB) and DXVK, creates a "Steam" bottle and installs Steam into it.

The bottom of the window shows what's happening and how far along it is.

## 4. Sign in to Steam and install a game

1. Steam for Windows opens — sign in with your account.
2. Install a game as usual. Once it's downloaded, it shows up in the Conversio library by itself (it refreshes every 15 seconds, or press ⌘R).
3. Hover over the cover and click **Play**.

## 5. For DirectX 12 games

Newer games such as GTA V Enhanced only run through Apple's D3DMetal. It's free, but you download it yourself — see the [D3DMetal guide](d3dmetal.md).

## Updates

Conversio tells you when a new version is out. Download the new DMG and replace the app in Applications — your bottles, games and settings are kept.
