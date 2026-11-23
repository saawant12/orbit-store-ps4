# Orbit Zero for PS4

Orbit Zero is Orbit’s app for Mac, Windows and Linux. With your PS4 it can:

- download games on your computer and send them to your PS4 over your home network, then install them. Your PS4 doesn’t need internet access for this;
- save games on your computer with no PS4 connected, and send them later;
- open Vikingfile and AkiraBox pages on your computer, where their Cloudflare check usually passes in seconds instead of minutes;
- hand a caught download link to your PS4, which then downloads the game itself;
- start Orbit on your PS4 from the computer;
- keep a PS5 and a PS4 as separate profiles, and switch between them in one click.

**Needs Orbit Store 0.0.2 or later on your PS4 and Orbit Zero 1.9.1 or later on your computer.** Orbit Zero 1.9.7 is attached to the [latest Orbit Store for PS4 release](https://github.com/saawant12/orbit-store-ps4/releases/latest). [Stream & install](#stream--install) needs Orbit Store 0.0.3 or later.

- **Installing Orbit Zero for the first time?** Follow [Install Orbit Zero](orbit-zero-installation.md).
- **PS4 without internet?** Follow [Set up Orbit on a PS4 without internet](orbit-zero-offline-ps4.md).

## What you need

- A Mac, Windows or Linux computer with internet access and enough free space for each download and any extracted files.
- A PS4 with GoldHEN, with its payload loader turned on once in **GoldHEN → Servers Settings → Enable PayLoader Server**.
- Writable storage on the PS4.
- Both devices on the same home network. Wi-Fi, Ethernet or one of each all work. Use the PS4’s local IPv4 address, such as `192.168.1.20`.

Packages are available for **ARM64 and x64 on macOS, Windows and Linux**; 32-bit x86 isn’t supported. The Mac app is Developer ID signed but not notarized; Windows and Linux packages are unsigned. [Install Orbit Zero](orbit-zero-installation.md) explains the first-launch prompts.

## Language and interface

Orbit Zero has 26 interface languages. In the Store interface, select the globe-shaped **Language** button in the top bar; in the other interfaces, open **Settings → Appearance → Language**. **System language** follows your computer.

Orbit Zero offers the same four interfaces as the PS4 app: **Store**, **Crossbar**, **Cinema** and **Panorama**. Select the palette-shaped **Appearance** button in Store’s top bar, or open **Settings → Appearance**, then select **Keep** and the layout’s name, such as **Keep Crossbar**, within 15 seconds. See [Appearance](appearance.md).

**Settings** has the same categories in every interface: **Downloads** (connections, retries, download preference and automatic shutdown), **Storage & cleanup** (download folder and cache), **Sources & accounts**, **Devices** (consoles and pairing) and **Updates & startup**. **Console** shows the connection, storage and transfers at a glance.

## Start Orbit from Orbit Zero

If Orbit isn’t running on your PS4 yet, start GoldHEN, then in Orbit Zero:

1. Open **Settings → Updates & startup**.
2. Enter your PS4’s IP address and choose **PS4**.
3. Select **Start Orbit on PS4**.

Zero gets Orbit for PS4 from the [latest release](https://github.com/saawant12/orbit-store-ps4/releases/latest), checks its checksum, keeps a copy on the computer and sends it to the ELF loader on port **9021**. If no ELF loader is running there, Zero first sends the elfldr included in Orbit Zero to GoldHEN’s payload loader on port **9090**, waits for elfldr to start, then sends Orbit. Port 9090 is only ever used to send elfldr. Orbit starts, and Zero connects to it.

When GitHub can’t be reached, Zero uses the last copy that passed its check. To send an ELF you downloaded yourself, open **Advanced** under **Start Orbit on PS4**, choose **Choose another ELF**, then select **Send custom ELF**.

If Orbit doesn’t start, close other homebrew apps such as ezRemote, then try again. Opening **Orbit Store** from the Games row starts Orbit too.

**On firmware 13.52 and 14.00, use Orbit Zero 1.9.2 or later.** Its elfldr supports these firmware versions. The elfldr in Orbit Zero 1.9.1 doesn’t, so with 1.9.1 start Orbit from the TV app or send `orbit_store.elf` to an ELF loader yourself.

## Connect and pair

1. In Orbit Zero, open **Settings → Devices**, enter your PS4’s IP address and select **Connect to Orbit**. After **Start Orbit on PS4**, Zero connects by itself.
2. Select **Show code on PS4**. The code appears as a notification on your PS4. To keep it on screen, open **App settings → Devices** in the TV app.
3. Enter the six-digit code and select **Pair with PS4**.

Zero saves the pairing in your computer’s encrypted credential store and reconnects by itself next time. macOS or Linux may ask to unlock the saved pairing. On macOS, allow Orbit Zero to access the local network when asked. If you denied it, turn it on in **System Settings → Privacy & Security → Local Network**, then reconnect.

Orbit’s port is **34177**. Don’t start a second copy of Orbit on the same port.

## Download now and send to your PS4 later

You don’t need a paired PS4 to download.

1. Open a game, choose its source and format, then select **Save to → This computer**.
2. Start the download. For Vikingfile or AkiraBox, Zero opens the provider page on the computer; see [Vikingfile, AkiraBox and archive downloads](#vikingfile-akirabox-and-archive-downloads).
3. Follow it in **Downloads**. **Show in folder** opens the saved file.
4. When you’re ready, pair your PS4, select **Send to PS4** on the finished download and choose a PS4 drive. The copy on your computer stays where it is.

## Browse PS4 games and add-ons

With a PS4 paired, **Browse** and **Add-ons** list only PS4 games and PS4 add-ons, as Orbit on your PS4 does. Filters, search, sorting, favourites and [saved filters](saved-filters.md) work as in the PS4 app. Open a game, choose a source and format, then choose a drive on your PS4 under **Save to**.

For add-ons, check the type, contents and the base game they need before choosing a source. A bundle doesn’t install everything by itself: after the transfer, choose **Install on PS4** for each package you want. See [Add-ons](add-ons.md).

### Get everything and game updates

**Needs Orbit Store 0.1.0 or later on your PS4 and Orbit Zero 1.9.5 or later.** On a PS4 game’s page, **Get everything** shows the same checklist as on the PS4: the game, its newest update and its DLC. In **Library**, Zero shows each game’s installed version, the update labels, the **Updates** filter and **Update all**. The PS4 downloads and installs these itself, so keep Orbit running on it. See [Get everything](downloads.md#get-everything) and [Game updates](library.md#game-updates).

### Free up space and download from links

**Needs Orbit Store 0.2.0 on your PS4 and Orbit Zero 1.9.7 or later.** When a game doesn’t fit on its PS4 drive, Zero offers [Free up space](downloads.md#free-up-space), as on the PS4. For a download that goes through your computer, Zero first checks that it can start, so nothing is deleted for a download that can’t. In Transfers, [Download from links](downloads.md#download-from-your-own-links) and **Replace link** work as on the PS4; your PS4 downloads the files itself.

## Choose where downloads run

| Download preference | New downloads |
| --- | --- |
| **Computer** (default) | Download on the computer, then send to the PS4. |
| **Prefer PS4** | The PS4 downloads the game itself when it can reach the source; otherwise the computer does. |

Change this under **Settings → Downloads → Download preference**. It applies to new downloads; running downloads keep their route. For **Computer** downloads, the computer handles provider access and artwork, so the PS4 needs only its home network connection. For the PS4 to download games itself, it needs internet access.

## Vikingfile, AkiraBox and archive downloads

On a PS4, Vikingfile and AkiraBox pages can take 2–3 minutes to pass their Cloudflare check. With Orbit Zero, the page opens in a separate window on your computer instead, where the check usually passes by itself in seconds. Complete any check that stays, then wait without pressing **Download**: Zero catches the ready link, closes the window and adds the download.

- With **Download preference → Computer**, Zero downloads the game on the computer and sends it to your PS4.
- With **Prefer PS4**, Zero hands the link it caught to your PS4, which checks it and downloads the game itself. The download appears in Orbit’s **Downloads** on your PS4 and in Zero. If your PS4 can’t use the link, Zero downloads the game on the computer instead.

The PS4 app points to Orbit Zero on those pages too.

**Vikingfile account.** Sign in under **Settings → Sources & accounts → Vikingfile** in Zero. Zero tries the signed-in session first and opens the page only when it needs a check. This sign-in is separate from the one on your PS4; see [Vikingfile](vikingfile.md).

**Expired links.** Select **Refresh download link** on a Vikingfile or AkiraBox download. Zero checks that the new link still points to the same file before reusing what’s already downloaded.

**ZIP, RAR and 7z.** Archives finish downloading and extract on the computer before their files are sent. Keep enough space for the archive and its extracted files together. **Settings → Storage & cleanup → Delete archives after extracting** is on by default. See [ZIP, RAR and 7z downloads](downloads.md#zip-rar-and-7z-downloads).

## Follow your downloads

**Downloads** shows **Download to computer** and **Transfer to PS4** as separate steps, each with its own speed and time left. A download your PS4 runs itself shows as **Direct PS4 download**. Finished computer downloads keep their real filenames; if a name already exists, Zero adds a number, such as `Game (2).pkg`.

## Download settings

- **Simultaneous downloads.** Zero downloads one game at a time by default. Choose **1–8** under **Settings → Downloads → Simultaneous computer downloads**. Files go to the PS4 one at a time while computer downloads continue.
- **Connections per download.** Choose **1–64** under **Settings → Downloads**; eight is the default. Zero uses fewer when the provider needs it.
- **Download folder.** **Settings → Storage & cleanup → Computer download folder → Choose folder**. New downloads use it; unfinished ones stay where they are so they can resume.
- **Download recovery.** **Settings → Downloads → Download recovery** sets retries, the wait between them and when a slow download reconnects. These apply to computer downloads; downloads your PS4 runs itself use the [settings on the PS4](downloads.md#download-recovery-settings).
- **Accounts.** **Settings → Sources & accounts** has **Archive.org** sign-in, **TorBox** and **Vikingfile**. They’re kept on the computer, separate from the accounts on your PS4. See [Archive.org sign-in](downloads.md#archiveorg-sign-in) and [TorBox](downloads.md#torbox).
- **Export a log.** For a bug report, **Settings → Diagnostics & about → Export log** saves recent activity and the paired PS4’s diagnostics, without game titles, filenames, folders, links, passwords or tokens. Nothing is uploaded by itself.

## Install on your PS4

When a transfer finishes, select **Install on PS4** on the download. Orbit installs the package on your PS4 and the game appears on the Games row and in **Library**. Orbit keeps the downloaded package unless you’ve turned on deleting packages after installation on the PS4. See [Install games](install-games.md).

Files go to the `homebrew` folder on the PS4 drive you chose. A finished download’s **Location** shows where it was saved on the PS4. For a game kept only on the computer, use **Show in folder**.

### Stream & install

**Needs Orbit Store 0.0.3 or later on your PS4.** **Stream & install** installs a finished computer download straight from your computer, without saving another copy of the package on the PS4 first. Your computer copy is kept.

1. Let the download finish on your computer, and connect your PS4.
2. In **Downloads**, select **Stream & install** on the game, then **Stream & install** again to start.
3. Keep Orbit Zero open and your computer awake until it shows **Installed on PS4**.

The PS4 still needs space for the installed game. Some packages can’t be installed straight from a computer; Orbit then tells you to send the package to the PS4 instead. Send it, then choose **Install on PS4**.

## Pause, reconnect and clean up

Keep Orbit Zero open and your computer awake during transfers, and keep the PS4 awake to receive files. If the PS4 disconnects, the computer can keep downloading. Reconnect the same PS4 and select **Resume**. Short connection drops are retried by themselves.

| Choose | What happens |
| --- | --- |
| **Resume** | Continues the transfer after checking the files already sent. |
| **Cancel and remove partials** | After you confirm, removes that transfer’s unfinished files from the computer and the PS4. |
| **Stop transfer** | Keeps the files on both sides and frees the queue. **This transfer can’t be resumed afterwards.** |
| **Restart PS4 transfer** | When offered, sends the saved computer copy again, without downloading it again. |
| **Remove from Downloads** | Removes the entry. You can keep the files, or review and delete the computer and PS4 copies. Installed games aren’t uninstalled. |

Computer copies are kept by default. **Settings → Storage & cleanup → Computer cache** can remove them after each successful transfer, or clear the finished ones now.

**Unpairing.** **Settings → Devices → Connection settings → Unpair PS4** forgets this PS4’s profile. Zero won’t unpair while transfers to that PS4 are unfinished; finish or cancel them first. Unpairing keeps files and download history.

## Change the PS4 drive

Use **Change drive** on a computer download whose copy on the computer is still there, including one already sent. Zero shows each drive’s free space, queued transfers and the space left after this transfer, and drives without enough space can’t be chosen. Only the transfer to the PS4 starts again; Zero reuses the computer copy.

## Let the PS4 turn off when work finishes

Open **Settings → Downloads → Automatic PS4 shutdown**, turn it on and choose **All downloads** or one download under **Wait for**. Other unfinished downloads, transfers and installations still keep the PS4 on. When everything is done, the PS4 shows a 60-second countdown you can cancel from Zero, the PS4 app or the browser. See [Automatic shutdown](shutdown.md).

## Reconnect after an address change

Open **Settings → Devices → Connection settings**, enter the PS4’s new IP address and select **Connect to Orbit**. Zero checks the saved pairing before moving your downloads to the new address.

If the PS4 no longer accepts the saved pairing, Zero offers **Pair again and keep downloads**. Confirm it’s the same PS4, show the code on it and enter it. Downloads stay paused until you select **Resume**; Zero compares the files already on the PS4 with the computer copy and continues from there when it can.

## Recover a finished computer download

If a finished download is still on your computer but its entry in **Downloads** is gone, open **Downloads → Recover downloads → Choose file** and pick the file from its original download folder. Check the game and the PS4 drive, then select **Add to queue**. Zero checks the file and adds it paused; select **Resume** to send it without downloading it again.

If an unfinished transfer on the PS4 blocks the queue after its entry was removed, use **Recover downloads → Review PS4 transfer**.

## Control it from your PS4

After pairing, open **App settings → Devices** in the PS4 app and select **Enable Orbit Zero**. Downloads you start on the PS4 then follow the download preference set on the computer: with **Computer**, Zero downloads them and sends them over. Keep Orbit Zero open. Turning it off affects new downloads only.

## PS5 and PS4 together

Orbit Zero uses one console at a time. Each console you pair gets its own profile, with its own address, pairing, games list and downloads. Your download folder, TorBox, Archive.org and Vikingfile sign-ins and language are shared.

- **Switch consoles:** **Settings → Devices → Consoles**, or the console buttons in the Connection panel on **Console**. Switching needs no new code.
- **Add a console:** select **Add another console**, then connect and pair it. Typing the address of a console you’ve already paired switches to its profile.
- Finish or cancel the transfers to one console before switching: they need that console to finish.
- **Unpair PS4** (or **Unpair PS5**) forgets only that console’s profile.

With a PS5 selected, Zero works as described in the [Orbit Store for PS5 guides](https://github.com/saawant12/orbit-store-ps5/blob/main/guides/orbit-zero.md).

## Updates

Open **Settings → Updates & startup**. Zero checks for updates when it opens and every six hours. When an update is ready, download the checked package and install it when you like; Zero never replaces itself or restarts by itself. See [Update Orbit Zero](orbit-zero-installation.md#update-orbit-zero).

Updating Orbit Zero doesn’t update Orbit on your PS4. Update that from **App settings → Updates & startup** on the PS4.

## Connect another app

In **Settings → Devices → Connected apps**, turn on **Allow other apps**, then approve the request from the other app or create a token for it. Each token can be removed on its own. Only apps on the same computer can connect. See [Connect another app to Orbit Zero](orbit-zero-integrations.md).

## Troubleshooting

- **Zero can’t find Orbit:** check that Orbit is running on your PS4 and that the IP address matches the one in Orbit’s settings. Both devices must be on the same network. On a Mac, check **Local Network** access for Orbit Zero.
- **“Neither an ELF loader nor GoldHEN’s payload loader answered”:** start GoldHEN and turn on its payload loader in **GoldHEN → Servers Settings → Enable PayLoader Server**.
- **“elfldr was sent, but no ELF loader started”:** close other homebrew apps such as ezRemote, then try again.
- **The pairing code isn’t accepted:** use the code currently on your PS4. Select **Show code on PS4** again if it has changed.
- **A transfer stopped:** reconnect the same PS4 and select **Resume**. Don’t unpair while transfers are unfinished.

See also [Troubleshooting](troubleshooting.md).
