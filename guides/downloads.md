# Find and download a game

**For Orbit Store 0.2.0 for PS4.** The catalogue has **1,739 PS4 games** with **1,856 single-file download options** from Archive.org, Vikingfile and AkiraBox. Open a game to choose from its sources and formats. What you see depends on which sources you turn on.

Settings paths in this guide use the Store layout. Crossbar, Cinema and Panorama call the main menu **Settings**; see [Appearance](appearance.md#find-settings-after-switching).

## Browse and choose

**Discover opens first.** In the default Store layout, start with the featured game and **New on Orbit**, then **Latest releases**. Move down to **All games** for the full collection. The grid loads more games as you scroll. Each game’s size is its smallest option from your enabled sources.

![Orbit Store 0.0.1 Discover on PS4 with BioShock Infinite: The Complete Edition selected](../assets/0.0.1/store-discover.jpg)

Switch to **Browse** for search and filters. It sorts by **Release date (newest first)**; games without a date follow alphabetically. Search by game name or title ID, filter by source, format, genre, tag, region or download size, and change the sort order. From 0.2.0, **Recently added** shows the games added to the catalogue most recently first. **Reset filters** goes back to the defaults. Source and Format allow several choices. **Installed games** hides games already installed on the PS4.

### Genres and filter counts

Browse filters show how many games match each choice, and update as you change your search and other filters. Choices with no matches are dimmed. This works in the TV app, the browser and Orbit Zero, in all four layouts.

![Browse in the PS4 TV app with Genre choices and matching game counts](../assets/0.0.1/store-genres.jpg)

Choose one or more entries under **Genre**. A game can match any selected genre while still meeting your other filters. Save the selection through [Saved filters](saved-filters.md). Only genres recorded for at least ten games appear in the list; games with missing or less common genres stay under **All genres**.

### Game tags

Use **Tags** for **PlayStation exclusive**, **Local co-op**, **Split-screen**, **Open world**, **Story-driven**, **Soulslike**, **Turn-based** and **PSVR supported**. Selecting several tags shows games matching any of them. Combine tags with Source, Format and the other filters.

PlayStation exclusive means no official PC, Xbox or Nintendo version. The PSVR tag covers required and optional VR modes; check the game details for headset needs. Tags are reviewed catalogue data and coverage is still growing, so an untagged game may still have the feature.

Save a game from its details page to find it under **Favourites** later; favourites are shared with your paired devices.

In the TV app’s Store layout, use the D-pad or left stick to move, Cross to select, Circle to go back and L1/R1 to switch tabs. Press **Square** on a game in Browse or Discover to add or remove it from Favourites. In the other layouts, **Triangle** toggles favourites; see [controls by layout](appearance.md#controller-navigation-in-the-tv-app). In the browser, use the arrow keys, Enter and Escape, or touch and mouse.

### Scores and playtimes

Game pages show Metacritic scores and HowLongToBeat estimates when recorded: 543 PS4 games have a score and 932 have playtimes. Browse can filter by minimum score or playtime and sort using these values. Choose **Main Story**, **Main + Extras** or **Completionist** for the estimate you want. These choices can be saved with Browse filters. Missing values stay unlabelled and sort last; applying a score or playtime filter excludes games missing that value. Playtimes are community estimates and vary by player. This information comes from the catalogue and can be corrected through catalogue updates.

To hide this information below game cards, turn off **Appearance → Scores and playtimes on game cards**. Game details and filters remain available. The preference is saved on the device and works in all four layouts.

## DLC and add-ons

Open **Add-ons** after Browse, or **Add-ons (count)** on a game’s details. Search by DLC or base-game name and filter by Type, Source and Region. Check the required game edition, title ID and known version requirements before downloading. See [the DLC guide](add-ons.md).

## Get everything

**Requires 0.1.0 or later.** On a game’s page, choose **Get everything** to download the game together with its newest update and every DLC Orbit has for it. It works in every look of the TV app and in the browser version. Orbit Zero 1.9.5 or later offers it on PS4 game pages too; your PS4 downloads and installs the items itself.

1. **Get everything** lists the game, using the source and format chosen on its page, then the newest update your PS4’s firmware can run, then each DLC with its source and size. Everything is ticked; untick anything you don’t want. If the game is already installed, its row shows **Installed** and the update appears only when it’s newer than the installed version.
2. Check the total size, the free space and the drive the downloads go to. If the drive doesn’t have room for everything ticked, Orbit says **Not enough space for everything on this drive.** and doesn’t start.
3. Choose **Download all**. Orbit adds the items to Downloads one after another and shows each one’s state, for example **Adding 3 of 14 to Downloads**. **Stop** stops adding the rest; anything already added stays in Downloads.
4. If an item needs its provider’s page, such as Vikingfile or AkiraBox, Orbit opens it on the PS4 as for a normal download, and the next item waits until that page adds its file. If the page is closed without a download, Orbit doesn’t add the items after it. Items that download from Archive.org or through TorBox need no page.
5. When the downloads finish, Orbit installs them in order: the game, then the update, then the DLC. If an earlier item fails or is removed, the ones after it wait; install the earlier one first, then select **Install** on the rest.

One Download all runs at a time. You can close Get everything while Orbit adds the items; open it again on the same game to see the progress.

## Pick a source, format and drive

Opening a game from filtered Browse results selects an option that matches those filters. Opening it elsewhere first tries the source and format you downloaded last, then an option that can download without a verification page. You can still choose another option.

On the game page, select the main download button to open **Download options**. This lets you review your choices without starting anything. Open **Source** to choose a format and provider, **Download using** for direct or TorBox delivery, and **Save to** for the PS4 drive. The storage panel shows **Free now**, **Unfinished downloads** and **After queue + this download**.

![Orbit Store 0.0.1 source, delivery and destination choices on PS4](../assets/0.0.1/store-download-options.jpg)

Known firmware requirements appear beside download options. Options that don’t suit your PS4’s firmware come last with a warning and stay selectable. Unknown requirements aren’t a promise of compatibility. If another format or version of the game is already installed, Orbit warns you and offers **Download anyway**.

### Which format to pick

| Format | What you get | What to do after it’s saved |
| --- | --- | --- |
| **PKG**, **FPKG** | `.pkg` package | Choose **Install on PS4** on the finished download. See [installing games](install-games.md). |
| **ZIP**, **RAR**, **7z** | Archive | Orbit unpacks it after downloading. When the contents are known, the label shows the format inside, for example `RAR · PKG`. |

Check the download size and expected unpacked size when planning drive space.

### Start the download

For a direct option, select **Download to PS4**. Orbit checks the file and the drive, then adds it to Downloads. For Vikingfile and AkiraBox, follow the provider steps below.

## Provider steps

Provider pages open full screen on the PS4, even when you start from a paired phone. With [Orbit Zero](orbit-zero.md), they open on the computer instead, where the check usually passes in seconds. Only one provider page can be open at a time; **Cancel verification** closes it without adding a download. If the page times out, start the option again. From 0.1.0, the TV app comes back to the front when the page closes. If the page closed before a download was added, Orbit says so; start the option again.

### Vikingfile

[Sign in to Vikingfile](vikingfile.md) first if you have an account. Choose the option and drive, then select **Download to PS4**. Orbit asks Vikingfile for the file with your session; if it gets a ready link, the download starts straight away.

If Vikingfile needs verification, its page opens. Complete the verification, move the pointer to **Download** with the left stick and press ○. Orbit checks the link against the file you chose, closes the page and returns to the app. Follow its progress in **Downloads**.

**Downloading through Orbit Zero?** Zero first asks Vikingfile for the file with its own saved sign-in. If verification is needed, Vikingfile opens on your computer. Complete any verification and wait without pressing **Download**. Zero catches the ready link and closes the page. With **Prefer PS4** in Zero’s **Settings → Downloads → Download preference**, Zero then hands the link to your PS4, which downloads the game itself; otherwise Zero downloads it and sends it over. See [Orbit Zero](orbit-zero.md#vikingfile-akirabox-and-archive-downloads).

![Vikingfile instructions in Download options: complete verification if shown, then select Download](../assets/0.0.1/store-download-options.jpg)

### AkiraBox

Choose the option and drive, then select **Open AkiraBox on PS4** in the TV app or **Open download page on PS4** in the browser. Complete any verification, then select **Download**. Orbit checks the link, closes the page and returns to the app.

AkiraBox may show an ad instead of the download. Close the ad and try again. If it keeps coming back, choose another source for the game. For a paused or failed AkiraBox download, use **Refresh download link**; Orbit keeps the partial file only if the new link points to the same file.

In Orbit Zero, AkiraBox opens on your computer. Complete any verification and wait without pressing **Download**: the page closes by itself once the file is ready, and the download appears in your queue.

## Accounts and TorBox

### Archive.org sign-in

Some Archive.org files need an account. Public downloads work without signing in.

Open **App settings → Sources & accounts → Archive.org** in the TV app or the browser. Enter your Archive.org email and password, select **Sign in**, and check that it says **Signed in**. Then try the download again. Orbit sends your details to Archive.org once and keeps only the sign-in on your PS4, never your password. The TV app and the browser share it. Sign out in the same place.

Orbit Zero keeps its own sign-in on the computer: open **Settings → Sources & accounts → Archive.org** in Zero. If you use **Prefer PS4**, sign in on the PS4 as well for downloads your PS4 runs itself.

Signing in helps with files that need an account; it doesn’t bring back files Archive.org has removed. If the page says the item is unavailable, choose another option.

### TorBox

TorBox is an optional way to download supported links. You need your own TorBox account; its plan, host list, quotas and file-size limits apply. You can keep using the original provider without it.

1. In the browser version, open **App settings → Sources & accounts → TorBox**. You can do this on the PS4 or a paired phone or computer.
2. Get your API key from [TorBox settings](https://torbox.app/settings), enter it and choose **Connect TorBox**. Keep the key private.
3. Open a game and its **Download options**. Select **Source**, then **Download using → TorBox**, and choose your drive.
4. Select **Download via TorBox**. Downloads shows the job as **via TorBox**.

Connect once in the browser; the TV app and paired devices share the connection. If you aren’t connected, choose **Set up TorBox** under **Download using**.

TorBox uses at most eight connections per game, even when you choose more. With TorBox connected, **Browse → Source → TorBox available** shows games with a supported option. If an option isn’t available through TorBox, choose the original provider; Orbit never switches a TorBox job to another method by itself. Disconnecting TorBox pauses its unfinished jobs and keeps their partial files; reconnect the same account to resume.

**TorBox in Orbit Zero.** Open **Settings → Sources & accounts → TorBox** in Zero and connect your API key on the computer, then choose **Download using → TorBox** on a supported option. Zero downloads to the computer; choose **This computer** to keep the game there, or a PS4 drive to send it over. This connection is separate from the PS4’s TorBox connection. Zero uses at most four connections per TorBox game.

### Remember your download method

Orbit remembers whether you chose **Direct** or **TorBox**. In **App settings → Sources & accounts → TorBox**, turn on **Always use TorBox** to use it for new downloads. Your account and the selected source must support the request. Turn this preference off before choosing Direct; Orbit doesn’t silently switch a TorBox request to the original source. Orbit Zero and the PS4 keep their own preferences.

## Download from your own links

**Requires 0.2.0 or later.** To download files that aren’t in the catalogue, open **Downloads** and select **Download from links**. Paste direct download links that start with `https://`, one per line, up to 20 at a time, and choose a drive. Orbit checks each link before adding it to Downloads, where it pauses, resumes and retries like a game. ZIP, 7z and RAR files unpack like games. Long links are easier to paste from a paired phone or computer.

If a link stops working, for example because it expired, select **Replace link** on that download and paste a fresh link to the same file. Orbit keeps the part already downloaded and carries on; a link to a different file is refused and the partial file is kept. Orbit Zero offers the same in Transfers; your PS4 downloads the files itself.

## ZIP, RAR and 7z downloads

Archive options are in the normal Format filter. Their size is the archive size. From 0.1.0, a ZIP, 7z or RAR download needs room only for itself when you add it. Orbit checks for room for the unpacked files just before unpacking; if there isn’t enough, the download waits, paused, with the archive kept. Select [Free up space](#free-up-space) on the download, or make room on its drive yourself, then select **Resume**. Multipart archives aren’t supported.

Orbit unpacks on the selected PS4 drive after downloading. Orbit Zero unpacks on the computer first, then sends the unpacked files to your PS4 drive. Follow the **Extracting** progress in Downloads. Orbit tries the known source passwords by itself (`DLPSGAME.COM`, `[DLPSGAME.COM]`, `SuperPSX`, `www.DLPSGAME.COM`, `downloadgameps3.com`, `hako` and `pippo`). If another password is needed, choose **Enter archive password**, then **Retry extraction**; Orbit reuses the downloaded archive.

**Delete archives after extracting** is on by default, under **App settings → Storage & cleanup** on the PS4, or **Settings → Storage & cleanup** in Orbit Zero. It removes the archive after a successful unpack and keeps archives that need a password or fail to unpack.

To unpack archives yourself with another tool, turn off **Extract archives after downloading** under **App settings → Storage & cleanup** on the PS4 (Orbit Store 0.1.0 or later). In the TV app’s Store look, select **Keep archives packed**. ZIP, 7z and RAR downloads you add afterwards are saved as the archive under its own name. Downloads already in the queue keep the setting they were added with. From 0.1.0, RAR archives Orbit unpacks use RARLAB’s UnRAR and several of the PS4’s CPU cores.

In Zero, the unpacked files on the computer follow the separate **Computer cache** setting. **Automatically remove after transfer** is off by default; turning it on removes those copies only after the PS4 confirms the transfer.

## Your download queue

### Follow your queue

Use **Active**, **Finished**, **Failed** and **Cancelled** to find a download. Move waiting items up or down, pause and resume, or cancel.

![Orbit Store 0.0.1 Downloads on PS4 with an empty queue](../assets/0.0.1/store-downloads.jpg)

Choose **1–64 connections per download** in **App settings → Downloads**; eight is the default. Active downloads share up to 64 connections. If a provider refuses several connections, Orbit retries with fewer. Speed depends on the provider, network and drive.

To remove a cancelled download and its partial file, use **Delete download** and confirm. Reconnect its drive first if it’s unplugged. If you kept the partial, resume it from Downloads.

Keep the PS4 awake. Closing the TV app or the browser leaves downloads running; stopping Orbit interrupts them. Downloads interrupted unexpectedly come back paused for you to check. **Restart Orbit** resumes downloads that were running before that restart. Orbit doesn’t download in rest mode.

**Notifications.** Open **App settings → Notifications** to choose PS4 alerts, phone or computer alerts through ntfy, or both. See [notifications](notifications.md).

### Remove download history and files

**Remove from history**, **Clear finished history** and **Clear cancelled history** let you choose what happens to the downloaded files.

1. Check the paths and file sizes.
2. Choose **Keep files** to remove only the history entry, or the delete option to remove the files too.
3. Optionally select **Remember my choice**. Reset it in **App settings → Storage & cleanup → Removing download history → Ask every time**.

Orbit protects files used by active downloads and installations. Reconnect a missing drive before deleting its files. If deleting fails, Orbit keeps the entry and shows the error. This removes downloaded files; it doesn’t uninstall a game.

In Orbit Zero, **Remove from Downloads** can include the computer copy, the PS4 copy or both. Check the selected copies before confirming. See [Pause, reconnect and clean up](orbit-zero.md#pause-reconnect-and-clean-up).

### Automatic PS4 shutdown

Open **App settings → Downloads → Automatic PS4 shutdown**. In Orbit Zero, use **Settings → Downloads** while connected to the PS4. Choose the whole queue or one download under **Wait for**, or choose **Shut down when finished** on a download and confirm. Other unfinished work still holds off shutdown. Orbit shows a 60-second countdown you can cancel. It’s off by default. See [Automatic shutdown](shutdown.md).

### Simultaneous downloads

Orbit downloads one game at a time by default. Choose **1–8** in **App settings → Downloads → Simultaneous downloads**. Games share the same connection and total speed; more games don’t add bandwidth. Lowering the limit lets current downloads finish first. Orbit Zero has its own setting, **Settings → Downloads → Simultaneous computer downloads**, and sends files to the PS4 one at a time while computer downloads continue.

### Download recovery settings

Open **App settings → Downloads → Download recovery**.

- **Automatic retries:** how many times Orbit tries again after a temporary failure, **0–10**; **0** turns retries off. The default is **3**.
- **Wait between retries:** **10 seconds** by default.
- **Wait before reconnecting** and **Reconnect below this speed:** when a download stays too slow, Orbit reconnects. By default, below **1 KiB/s** for **60 seconds**.

Changes apply on the next attempt. Your partial file is kept, but a paused download still needs **Resume**. Retries can’t fix a removed file, an account limit or a full drive.

These settings apply to downloads your PS4 runs. For computer downloads, use **Settings → Downloads → Download recovery** in Orbit Zero. The computer and the PS4 keep separate settings.

## Where downloads are saved

Downloads and Orbit Zero transfers go to the selected drive’s `homebrew` folder:

| Drive | Folder on the PS4 |
| --- | --- |
| Internal storage | `/data/homebrew/` |
| USB drive | `/mnt/usb0/homebrew/`, `/mnt/usb1/homebrew/`, or the folder for the selected USB drive |

USB numbering depends on how the console mounts your drives. Choose by the label Orbit shows and keep that drive connected. Orbit creates `homebrew` when needed and checks it can write there before downloading or resuming. A drive attached to your phone or computer isn’t a PS4 destination.

**Downloads → Finished → Location** shows the saved file or unpacked folder in the TV app and the browser. It’s where the file was saved; it doesn’t check whether it has since been moved or deleted, and it doesn’t mean the game is installed.

Orbit Zero also keeps a copy in the computer’s download folder unless you turn on removal after transfer; see [Download settings](orbit-zero.md#download-settings). Zero’s download details show the PS4 **Location**. **Settings → Storage & cleanup → Computer download folder** sets where new computer downloads go; unfinished ones stay in their original folder.

### Choose a drive with enough space

Check the space estimate before starting. Orbit prefers your default drive while it has room; otherwise it suggests another drive with more space. A drive you chose yourself is never swapped silently. While an archive is unpacked, it and its files need space at the same time; Orbit checks for that room just before unpacking (see [ZIP, RAR and 7z downloads](#zip-rar-and-7z-downloads)). Installing needs space on the PS4 too.

### Free up space

**Requires 0.2.0 or later.** When a game doesn’t fit on its drive, **Download** no longer stays greyed out. It opens **Not enough space**, which lists what Orbit could delete from that drive to make room, biggest first:

- **Left by Orbit** is ticked for you: packages your PS4 has already installed, archives kept after unpacking and downloads you cancelled.
- **Games** lists the games installed on that drive for you to choose; none is ticked. Orbit uninstalls a game you tick, as from the PS4 home screen. USB drives list no games, and homebrew apps and Orbit itself are never listed.

Select **Delete and download**. Orbit deletes what you picked one at a time, says how much it freed, then starts the download. Saves are not touched. If Orbit kept the package of a game you uninstalled, **Install** is offered for it in **Downloads** again. **Free up space** is also in Library and on a download that paused because there wasn’t room to unpack it.

Orbit Zero shows each PS4 drive’s free space and the space left after queued transfers, offers **Free up space** for a drive known to be too small and checks the computer’s space too. It first checks that the download can start, so nothing is deleted for a download that can’t. For a Zero transfer already in the queue, [Change drive](orbit-zero.md#change-the-ps4-drive) reuses the computer copy.

## Get new games and corrected details

Orbit checks for catalogue updates when it starts and every six hours. Use **App settings → Game catalogue → Refresh catalogue** to check now. You can browse the saved catalogue offline, and queued downloads keep the files you chose. New games and corrected details arrive without reinstalling Orbit.

[Getting started](getting-started.md) · [Install games](install-games.md) · [Troubleshooting](troubleshooting.md)
