# ROT

An idle Ragnarok Online–style RPG that lives in your taskbar. Your hero hunts monsters in a slim
strip docked above the taskbar (Windows) or your desktop's panel (Linux), levels up, changes jobs,
learns skills and loots items and cards while the game runs. Friends can join you in online co-op.

This repository holds the game's releases only: no code.

**[Download the latest release](https://github.com/ghervis/rot-releases/releases/latest)**

## What you need

- Windows 10 or 11, 64-bit; or 64-bit Linux with an X11 desktop, or a Wayland one with XWayland
  (GNOME, KDE Plasma and most others have it), and a compositor for the strip's see-through
  background (every desktop has one).
- A Ragnarok Online client installed (its folder, with its `data.grf`). On Linux, a Windows client
  installed under Wine, or its folder copied over from Windows. The game ships no Ragnarok
  Online art or sound: it reads them from your own client the first time it starts. A client whose
  GRF files are encrypted for a private server can't be read.

## Install

### Windows

1. On the [latest release](https://github.com/ghervis/rot-releases/releases/latest), under
   **Assets**, download `ROT-<version>-windows.zip`.
2. Right-click the zip, **Extract All…**, and pick a folder of your own, such as `C:\Games` or your
   Documents. **Not** `Program Files`: the game updates itself in its own folder and needs to
   write there.
3. Open the `ROT` folder it made and run **`ROT.exe`**. Keep the five files together (`ROT.exe`,
   `ROT.pck` and the three `.dll` files).
4. Windows may say **"Windows protected your PC"** (the game isn't code-signed): click
   **More info**, then **Run anyway**. It asks only the first time.
5. The first screen asks for your Ragnarok Online client's folder: **Detect installed client**
   usually finds it, or choose it yourself. The game copies the sprites, icons and sounds it needs
   (a few seconds). Nothing is uploaded anywhere.
6. Create your hero and start.

### Linux

1. On the [latest release](https://github.com/ghervis/rot-releases/releases/latest), under
   **Assets**, download `ROT-<version>-linux.zip`.
2. Unzip it into a folder of your own, such as `~/Games`, with your file manager's **Extract** or:
   ```bash
   unzip ~/Downloads/ROT-*-linux.zip -d ~/Games
   ```
   The game updates itself in its own folder and needs to write there.
3. Run **`ROT.x86_64`** in the `ROT` folder it made (double-click it, or `~/Games/ROT/ROT.x86_64`).
   Keep the four files together (`ROT.x86_64`, `ROT.pck` and the two `.so` files). If it says
   **"Permission denied"**, make it executable first: `chmod +x ~/Games/ROT/ROT.x86_64`.
4. The first screen asks for your Ragnarok Online client's folder: **Detect installed client**
   looks in your Wine prefixes (`~/.wine`, and Lutris', Bottles', PlayOnLinux's and Steam
   Proton's), or choose it yourself. The game copies the sprites, icons and sounds it needs (a few
   seconds). Nothing is uploaded anywhere.
5. Create your hero and start.

The game has no tray icon on Linux: the strip's own buttons and right-click menu do everything,
**Quit** included. It runs as an X11 window (through XWayland on a Wayland desktop), the strip sized
by your desktop's scaling.

### Playing

The strip docks above the taskbar (or panel) on the right. The **☰** button opens the menu; right-click the
strip for its other commands. Drag the strip to move it; the arrow in its corner docks it again.
Nothing happens while the game is closed.

## Updates

The game updates itself:

- It checks for a new version a minute after it starts, and every 6 hours while it runs.
- It downloads the new version in the background (usually about 5 MB) and puts it in as you
  close the game.
- **Restart to update** puts it in now: Settings → Updates, the strip's right-click menu or (on
  Windows) the tray icon's.

Settings → **Updates** shows your version, checks now, and turns the automatic checks off. A game
in a folder it can't write to links this page instead: download the new zip and extract it over the
old folder, replacing its files.

## Your saves

Your characters, Account Inventory and settings aren't in the game's folder. They're in
`%APPDATA%\Godot\app_userdata\TaskbaRO\` on Windows (paste that into Explorer's address bar) and
`~/.local/share/Godot/app_userdata/TaskbaRO/` on Linux, with the art imported from your client.
Updating or deleting the game's folder leaves them as they are.

- **Back them up** by copying that folder.
- **Play the same account on another PC:** Settings → **Cloud Save**.
- A save made by a newer version isn't opened by an older one: update the game to play it.

## Uninstall

Close the game and delete its folder. To delete your saves and the imported art too, delete
`%APPDATA%\Godot\app_userdata\TaskbaRO\` (Linux: `~/.local/share/Godot/app_userdata/TaskbaRO/`)
as well.

## Trouble

- **The update didn't go in:** another window of the game was still open as it closed. Close every
  one; it tries again the next time the game closes.
- **No sprites:** Settings → **Client Folder** shows the folder and its GRF files, and
  **Choose folder…** picks another.
- **Linux: the strip is on a black box:** your desktop runs without a compositor. Turn its
  compositing on (Xfce: Settings → Window Manager Tweaks → Compositor).
- **Linux: the strip is too big or too small:** it follows your desktop's scaling for X11 apps
  (`xrdb -query | grep -i dpi` shows it: 96 is 100%, 144 is 150%). Change the scaling in your
  desktop's display settings and restart the game.

## Legal

ROT is an unofficial fan project, not affiliated with or endorsed by Gravity Co., Ltd.
*Ragnarok Online* and its assets belong to Gravity. The game ships no Gravity assets: sprites,
icons, sounds and the world map are read from a client you supply. Monster, item and map data are
derived from rAthena (GPL-3.0). Online play uses Epic Online Services under Epic's terms.
