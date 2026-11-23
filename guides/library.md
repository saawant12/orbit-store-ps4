# Your Library and storage

**For Orbit Store 0.2.0 for PS4.** Library is in the TV app, the browser and [Orbit Zero](orbit-zero.md) on a computer paired with the PS4. All three show the same PS4 games and drives. Store, Crossbar, Cinema and Panorama show it in different layouts; changing [appearance](appearance.md) doesn’t change which games are installed.

Library shows the games installed on your PS4. Orbit reads them from the console itself; you don’t need ShadowMount or any other tool. It works independently of your download-source choices.

## Understand the labels

- **Installed:** the game is installed on the PS4. From 0.1.0, Library also shows the installed version, for example **Installed 1.04**.
- **On drive:** the game’s files are on that drive.
- **Update {version}:** a newer update for the game is in Orbit’s catalogue and runs on your PS4’s firmware. See [Game updates](#game-updates).

Search by title, title ID or path, and filter by status, location or format.

## Game updates

**Requires 0.1.0 or later.** Orbit compares each installed game’s version with the newest update in its catalogue that your PS4’s firmware can run, including backports for older firmware. Orbit has updates for 410 PS4 games.

When a game has a newer update, Library marks it with **Update** and the version. **Updates**, with the number of games, then appears: a tab in the Store and Cinema looks, a row next to Installed in Crossbar, a group after your games in Panorama, and a filter in the browser and Orbit Zero. It lists only games with an update.

- Select **Update** on a game, or **Update all** for every game in the list. Update all adds up to 64 updates at a time; select it again for the rest.
- Updates download and install by themselves; follow them in **Downloads**. Library shows the new version once the PS4 has installed it.
- An update that needs its provider’s page, such as Vikingfile or AkiraBox, opens it on the PS4 as for a normal download.

Orbit doesn’t send a notification about updates; check **Updates** in Library. With a PS4 paired, Orbit Zero 1.9.5 or later shows the same update labels, the **Updates** filter and **Update all**; the PS4 downloads and installs the updates itself.

## Downloads and Library

Library shows installed games, while Browse uses Orbit’s download catalogue. A finished download is a saved file, not an installed game. Choose **Install on PS4** on the download to install it; it then appears in Library. See [installing games](install-games.md).

To find a finished download’s file, open **Downloads → Finished → Location** in the TV app or the browser. That saved path is separate from Library. In Orbit Zero, a download’s **Location** shows where it was saved on the PS4; for a download kept on the computer, use **Show in folder**.

## DLC and installed games

The **Add-ons** page is a separate collection. Finding the base game in Library doesn’t mark its DLC as installed or confirm that an add-on matches its edition or version. Check the add-on’s requirements and its own installation status in Downloads. See [the DLC guide](add-ons.md).

## Automatic updates

Library and drive information refresh by themselves. Game sizes show **Measuring…** until they’re known. After an installation, or when a drive is connected, Orbit reads the installed games again; **Looking for new games…** shows while it does. **Try again** appears if the list can’t be read. **Scan for games** stays available as a manual fallback.

## Manage storage

Open **Library → Files** to check free space and manage files and folders on internal storage and USB drives. Select a folder to open it; Circle goes back one folder. See the [Files guide](files.md).

**Requires 0.2.0 or later.** Select **Free up space** in Library to make room on a drive. Orbit lists its own leftovers, ticked for you, and the games installed on that drive for you to choose; it uninstalls a game only when you tick it. Saves are not touched. See [Free up space](downloads.md#free-up-space).

Orbit doesn’t start, copy or move installed games, and uninstalls one only through **Free up space**. You can also uninstall games from the PS4 home screen. Downloads and Library are separate: a finished download isn’t a promise that the game is installed or ready to play.

[Getting started](getting-started.md) · [Downloads](downloads.md) · [Files](files.md) · [Troubleshooting](troubleshooting.md)
