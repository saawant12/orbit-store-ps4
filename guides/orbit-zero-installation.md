# Install Orbit Zero

Orbit Zero downloads games on your computer and sends them to your PS4 over your home network. Wi-Fi and Ethernet both work, including when one device uses Wi-Fi and the other uses a cable. The PS4 doesn’t need internet access for computer downloads.

This guide covers **Orbit Zero 1.9.7** with **Orbit Store for PS4 0.0.2** or later. Get the files from the [Orbit Store for PS4 release](https://github.com/saawant12/orbit-store-ps4/releases/latest).

- **Installing for the first time?** Follow this guide in order: choose and verify your download, install it on your computer, then connect your PS4.
- **Already using Orbit Zero?** Go to [Update Orbit Zero](#update-orbit-zero).
- **PS4 has no internet?** Follow [Set up Orbit on a PS4 without internet](orbit-zero-offline-ps4.md).
- **Using Orbit Zero day to day?** See [Orbit Zero for PS4](orbit-zero.md).

## Choose your download

| Computer | File |
| --- | --- |
| Mac with an Apple M-series chip | `Orbit-Zero-1.9.7-mac-arm64.dmg` |
| Mac with an Intel processor | `Orbit-Zero-1.9.7-mac-x64.dmg` |
| Windows on Intel or AMD | `Orbit-Zero-1.9.7-win-x64.exe` (installer) or `Orbit-Zero-1.9.7-win-x64.zip` (portable) |
| Windows on ARM, including Snapdragon | `Orbit-Zero-1.9.7-win-arm64.exe` (installer) or `Orbit-Zero-1.9.7-win-arm64.zip` (portable) |
| Ubuntu or Debian on Intel or AMD | `Orbit-Zero-1.9.7-linux-amd64.deb` |
| Ubuntu or Debian on ARM64 | `Orbit-Zero-1.9.7-linux-arm64.deb` |

Not sure which one you need? On a Mac, check **Apple menu → About This Mac**. On Windows, check **Settings → System → About → System type**. On Linux, run `uname -m`: `x86_64` needs AMD64/x64; `aarch64` needs ARM64. In a virtual machine, choose the build for the guest operating system. 32-bit x86 isn’t supported.

The Mac app is Developer ID signed but isn’t notarized yet. Windows and Linux packages are unsigned. The installation steps below explain the security prompts this can cause.

The same Orbit Zero works with a PS5 too; see [PS5 and PS4 together](orbit-zero.md#ps5-and-ps4-together).

## Verify your download

Download **`SHA256SUMS`** from the same release as your desktop package. It has a SHA-256 checksum for each file. Compute the checksum of the file you downloaded with one of the commands below, replacing the filename if you chose a different build.

**macOS, in Terminal:**

```sh
shasum -a 256 "$HOME/Downloads/Orbit-Zero-1.9.7-mac-arm64.dmg"
```

**Windows, in PowerShell:**

```powershell
Get-FileHash "$env:USERPROFILE\Downloads\Orbit-Zero-1.9.7-win-x64.zip" -Algorithm SHA256
```

**Linux, in a terminal:**

```sh
sha256sum "$HOME/Downloads/Orbit-Zero-1.9.7-linux-amd64.deb"
```

Open `SHA256SUMS` in a text editor and find the line with the **exact same filename**. Its 64-character checksum must match your result; uppercase and lowercase letters are equivalent. If it differs, download the file again before installing. You only need the package for your computer, not every file listed in `SHA256SUMS`.

The PS4 ELF and PKG have their own `.sha256` files; see [Verify the PS4 files](getting-started.md#verify-the-ps4-files).

## Install on your computer

Follow the steps for your operating system. Each section also covers the permission and security prompts you may see the first time you open the app.

### macOS

1. Quit any open copy of Orbit Zero.
2. Open the matching `.dmg` and drag **Orbit Zero** into **Applications**. If updating, choose **Replace**.
3. Eject the disk image and open **Orbit Zero** from Applications. Keep using this installed copy rather than opening it from the disk image.
4. If macOS says it can’t verify the app, first check that you downloaded it from the official release. Then open **System Settings → Privacy & Security → Open Anyway** and confirm **Open**. The Mac app isn’t notarized; see [Apple’s instructions](https://support.apple.com/en-us/102445).
5. When connecting, allow **Orbit Zero** to access your local network. If you denied it before, turn on Orbit Zero in **System Settings → Privacy & Security → Local Network**, reopen the app and try again. This lets it reach your PS4; it’s separate from internet access. See [Apple’s local network guidance](https://developer.apple.com/documentation/technotes/tn3179-understanding-local-network-privacy).

**Keychain prompts.** Pairing or selecting **Reconnect** may open a Keychain prompt to protect or unlock your saved pairing. Approve the Orbit Zero request to continue, and enter your Mac login password only in the macOS prompt if asked. When you reopen the app, it checks your saved PS4 and may unlock Keychain to reconnect. You won’t see a Keychain prompt while the console is offline.

### Windows

**Installer (normal installation)**

1. Download the `.exe` matching your processor.
2. Quit Orbit Zero, then run the installer. Check any Windows security prompt against the file you downloaded from the official release.
3. Open Orbit Zero from the Start menu.

**Portable ZIP**

The installer is optional. The ZIP has no installation wizard, and **Run as administrator** isn’t needed.

1. Save the matching ZIP to a folder on the Windows computer, such as **Downloads**.
2. Right-click it and choose **Extract All**. Keep the whole extracted folder together.
3. Open **Orbit Zero.exe** from that folder. Don’t open it from inside the ZIP or copy only the EXE out of the folder. You can create a shortcut to the extracted EXE.

**Security and network prompts (installer or ZIP)**

- If SmartScreen says **Windows protected your PC**, check that this is the Orbit file you meant to download. For a trusted copy, choose **More info → Run anyway**, if offered. The Windows app is unsigned. If your organisation or Smart App Control blocks it without that option, contact the maintainer or administrator rather than turning protection off. See [Microsoft’s SmartScreen guidance](https://learn.microsoft.com/en-us/windows/apps/package-and-deploy/smartscreen-reputation).
- If Windows asks to allow network access, allow **Orbit Zero** on your trusted **Private** home network. This lets the PS4 reach the computer. Firewall approval may need an administrator; the app itself runs as your normal user. See [Microsoft’s firewall guidance](https://support.microsoft.com/en-us/windows/security/firewall/risks-of-allowing-apps-through-windows-firewall).

**Using a virtual machine?** Copy the ZIP onto the Windows drive before extracting it. If the shared folder says **Access denied**, move the ZIP with the VM’s own file-transfer method or download it inside Windows. Changing Orbit’s permissions won’t fix the VM’s shared folder.

### Ubuntu and Debian

Use the `.deb` installer. It adds Orbit Zero to your application menu and sets up the browser sandbox for you.

1. Save the matching `.deb` in **Downloads** on the Linux computer, not inside a shared folder.
2. Open a terminal and run **one** of these, matching your processor:

   ```sh
   # Intel / AMD 64-bit
   sudo apt install "$HOME/Downloads/Orbit-Zero-1.9.7-linux-amd64.deb"
   ```

   ```sh
   # ARM64
   sudo apt install "$HOME/Downloads/Orbit-Zero-1.9.7-linux-arm64.deb"
   ```

3. Enter your Linux password if asked. The installer needs administrator access; characters don’t appear while you type the password. Internet access may be needed to install dependencies.
4. Open **Orbit Zero** from your application menu. Don’t run the app itself with `sudo`.

**Saved the installer somewhere else?** Open a terminal in that folder and put `./` before its filename, for example `sudo apt install ./Orbit-Zero-1.9.7-linux-arm64.deb`. Without `./` or a full path, apt searches its package lists and reports **Unable to locate package**. If `uname -m` says `aarch64`, use the ARM64 installer; AMD64 is for Intel and AMD computers.

**Keyring prompts.** When pairing or reconnecting, Ubuntu may ask you to unlock your login keyring, which stores the pairing securely.

### Other Linux systems or the portable archive

`Orbit-Zero-1.9.7-linux-x64.tar.gz` and `Orbit-Zero-1.9.7-linux-arm64.tar.gz` contain the portable app. Compatibility can vary between distributions; on Ubuntu or Debian, use the installer above.

Extract the **whole archive** onto the Linux drive in a path without spaces or brackets, such as `~/orbit-zero`. From the folder with the app, run:

```sh
./orbit-zero
```

If it says **chrome-sandbox** isn’t configured correctly, run these two commands from the same folder, then open it normally:

```sh
sudo chown root:root chrome-sandbox
sudo chmod 4755 chrome-sandbox
./orbit-zero
```

`chrome-sandbox` is the browser engine’s security helper. The Ubuntu and Debian installer sets it up for you. If sandbox or AppArmor errors continue on Ubuntu, use the `.deb` rather than turning sandboxing off.

## Set up the app

### Choose your language

Select the globe-shaped **Language** button in Store’s top bar, or **Settings → Appearance → Language** in Crossbar, Cinema or Panorama. Orbit Zero supports English, Arabic, Czech, Danish, Dutch, Finnish, French, German, Greek, Hungarian, Indonesian, Italian, Japanese, Korean, Norwegian Bokmål, Polish, Portuguese (Brazil), Portuguese (Portugal), Romanian, Russian, Spanish, Swedish, Turkish, Ukrainian, Simplified Chinese and Traditional Chinese. Choose **System language** to follow your computer. This changes Orbit’s interface, not a downloaded game’s language.

### Choose your interface

Use the palette-shaped **Appearance** button in Store’s top bar to choose Store, Crossbar, Cinema or Panorama. After switching, select **Keep** and the layout’s name, such as **Keep Crossbar**, within 15 seconds, or Zero switches back. In the other layouts, go back to **Settings → Appearance** to change it again. See the [appearance guide](appearance.md) for the four layouts. Your choice is saved separately from the PS4 app’s appearance.

## Download without connecting a PS4

You can start downloading straight away. Open a game, choose its download option and select **Save to → This computer**. No pairing or running Orbit on the PS4 is needed. When the download finishes, use **Show in folder** to find it. Connect your PS4 later and choose **Send to PS4** in Downloads when you want to transfer the game. See [Download now and send to your PS4 later](orbit-zero.md#download-now-and-send-to-your-ps4-later).

## Connect your PS4

Keep the computer and PS4 on the same home network. Wi-Fi and Ethernet both work; the PS4 doesn’t need internet. Avoid guest Wi-Fi or network isolation that stops devices from reaching each other. Keep both devices awake during transfers.

You need **Orbit Store 0.0.2 or later** on the PS4. Older versions don’t accept files from Orbit Zero.

### Start Orbit on your PS4

1. On the PS4, start **GoldHEN**. Turn on its payload loader once in **GoldHEN → Servers Settings → Enable PayLoader Server**. Orbit Zero doesn’t jailbreak the console.
2. In Orbit Zero, open **Settings → Updates & startup**. Enter the PS4’s IP address, which you can find in **Settings → Network → View Connection Status** on the PS4. Leave **Orbit port** at **34177** unless you changed it.
3. Choose **PS4**, then select **Start Orbit on PS4**.

Orbit Zero gets Orbit for PS4 from GitHub on the computer, checks it and sends it to the ELF loader on port **9021**. If no ELF loader is running, Zero first starts its included elfldr through GoldHEN’s payload loader on port **9090**. Zero then waits for Orbit to start and connects by itself. The PS4 never visits GitHub.

If Orbit is already running, for example from the TV app, use **Settings → Devices → Connect to Orbit** instead. If Orbit doesn’t start, close other homebrew apps such as ezRemote, then try again.

Prefer to download the ELF yourself? See [Manual fallback: download the ELF yourself](#manual-fallback-download-the-elf-yourself).

### Pair with your PS4

1. When **Pairing required** appears, open **Settings → Devices** and select **Show code on PS4**.
2. Enter the six-digit code from the PS4 notification, then select **Pair with PS4**. If you miss the notification, ask for it again after the countdown, or open **App settings → Devices** in the TV app, which keeps the code on screen.
3. Allow access to your computer’s credential store if asked, so Zero can save the pairing securely.

If you’ve already paired this PS4, Zero uses that pairing again when it connects. You only need a new code if the pairing was removed or no longer works.

### Check your connection and storage

When the status changes to **Connected**, your PS4 drives appear in **Console** and **Settings → Storage & cleanup**.

You’re ready to download. With a PS4 connected, Browse and Add-ons list PS4 games and add-ons only. Open a game, choose a source and a PS4 drive, and start the download. **Downloads** shows the computer download and the PS4 transfer separately.

When the files reach the PS4, select **Install on PS4** for a PKG. See [Install on your PS4](orbit-zero.md#install-on-your-ps4). With Orbit Store 0.0.3 or later, [Stream & install](orbit-zero.md#stream--install) can instead install a finished computer download straight from the computer, without a copy on the PS4.

### Choose where downloads run

Leave **Settings → Downloads → Download preference → Computer** selected to download through your computer, whether or not the PS4 has internet. Choose **Prefer PS4** to let the PS4 download directly when it can reach that source, with the computer as the fallback. For Vikingfile and AkiraBox, **Prefer PS4** means the page opens on the computer and Zero then hands the download link to your PS4. This preference applies to new downloads.

### Reconnect and control from the PS4

After reopening the app, Orbit Zero reconnects to your saved PS4 by itself. If the PS4 is offline or you declined credential access, use **Console → Reconnect** when ready.

To control the computer’s downloads from your TV, install the TV app from the same release, then select **App settings → Devices → Enable Orbit Zero**. See [Control it from your PS4](orbit-zero.md#control-it-from-your-ps4).

## If the connection fails

- **“Neither an ELF loader nor GoldHEN’s payload loader answered”:** start GoldHEN and turn on **Enable PayLoader Server**, then try again.
- **“elfldr was sent, but no ELF loader started”:** close other homebrew apps such as ezRemote, then try again.
- **“Could not get Orbit for PS4 from GitHub”:** the computer needs internet for this step. Or [download the ELF yourself](#manual-fallback-download-the-elf-yourself).
- **Could not reach Orbit on port 34177:** start Orbit using the steps above, check the PS4’s current IP address, and check local network or firewall permission on the computer.
- **Pairing code is missing:** select **Show code on PS4** and watch for the console notification.
- **No drives appear:** check that the drive is connected and available to Orbit on the PS4, then refresh the Console view.
- **Transfer stopped after sleep:** wake both devices, reconnect the same PS4 and select **Resume**. Keep the partial files. If the PS4’s address or pairing changed, see [Reconnect after an address change](orbit-zero.md#reconnect-after-an-address-change). A transfer ended with **Stop transfer** can’t resume; see [Pause, reconnect and clean up](orbit-zero.md#pause-reconnect-and-clean-up).

For new downloads, keep enough space on the computer for the whole file. Keep Orbit Zero open while downloading or transferring.

## Manual fallback: download the ELF yourself

Orbit Zero gets Orbit for PS4 for you, so this is optional. To download and choose the ELF yourself:

1. On your **computer**, open the [Orbit Store for PS4 release](https://github.com/saawant12/orbit-store-ps4/releases/latest). Under **Assets**, download **`orbit_store.elf`** and **`orbit_store.elf.sha256`**, then [check the checksum](getting-started.md#verify-the-ps4-files).
2. Start GoldHEN on the PS4. In Orbit Zero, open **Settings → Updates & startup**, enter the PS4’s IP address and choose **PS4**.
3. Expand **Advanced**. Check **ELF loader port**: normally **9021**.
4. Select **Choose another ELF** and choose the downloaded **`orbit_store.elf`**.
5. Select **Send custom ELF**. Zero sends that file, waits for Orbit to start and connects by itself. Complete the [pairing steps](#pair-with-your-ps4) if asked.

The GitHub download happens on your computer; **the PS4 still doesn’t need internet**. If an older Orbit is already running, stop it first in the browser version under **App settings → Updates & startup → Stop Orbit to restart**, then send the new file. Sending a file doesn’t replace a running Orbit.

## Next steps

- [Download settings](orbit-zero.md#download-settings): how many games download at once, the computer download folder and computer cache cleanup.
- [Vikingfile, AkiraBox and archive downloads](orbit-zero.md#vikingfile-akirabox-and-archive-downloads).
- [Follow your downloads](orbit-zero.md#follow-your-downloads) and [Pause, reconnect and clean up](orbit-zero.md#pause-reconnect-and-clean-up).

## Update Orbit Zero

Replace the desktop app with the newer version. Your pairing and queue stay saved.

### Update checks in Orbit Zero

Open **Settings → Updates & startup** in any layout to see your installed version or check by hand. Store also keeps its **Updates** shortcut. **Check for updates automatically** is on by default: Orbit Zero checks its official GitHub release when it opens and every six hours. You can turn this off in the same place.

When **Update available** appears, select **Download update**. Zero picks the package for your operating system and processor, then checks its size and SHA-256 before offering **Open installer** (Mac and Linux) or **Open ZIP** (Windows). You can cancel an update download without affecting game transfers.

### Install the desktop update

Installing is your choice. Finish or pause transfers and quit Orbit Zero before replacing it.

- **Mac:** drag the app from the DMG into Applications and choose **Replace**.
- **Windows:** run the new installer, or extract the new ZIP into a new folder and open **Orbit Zero.exe** from that copy. Your pairing and queue stay in your Windows user profile.
- **Ubuntu and Debian:** install the new `.deb` the same way as above, or open it with your package installer. Your pairing and queue stay in your user profile. Other Linux systems can use the portable archive.

### Update Orbit on your PS4

Updating Orbit Zero doesn’t update Orbit on your PS4. With internet on the PS4, use **Update Orbit** under **App settings → Updates & startup**; see [Update Orbit](getting-started.md#update-orbit).

Without internet on the PS4:

1. In the browser version, stop Orbit under **App settings → Updates & startup → Stop Orbit to restart**.
2. In Orbit Zero, select **Start Orbit on PS4**. Zero gets the newest Orbit for PS4 from GitHub on the computer and starts it.
3. Select **Resume** for any paused transfers.

To update the TV app itself without internet on the PS4, install the newer `orbit_store_ps4.pkg` from a USB drive; see [Set up Orbit on a PS4 without internet](orbit-zero-offline-ps4.md#optional-the-tv-app-on-your-ps4).

## Connections per download

In **Settings → Downloads → Connections per download**, choose **1–64**, with eight as the default. More connections help only when the provider and network allow them. Orbit can retry with fewer connections when a host refuses. This is separate from how many games download at once.
