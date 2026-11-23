# Get started with Orbit Store

**For Orbit Store 0.2.0 for PS4 (beta).** Tested on a PS4 on firmware 12.00 with GoldHEN. 0.0.3 added support for firmware 13.52 and 14.00, which hasn’t been tested on a console yet.

Orbit runs on your PS4. Use the TV with your controller, or pair a phone or computer to manage the same catalogue and download queue. Files go to the PS4's selected storage.

**Ways to use Orbit**

| Do this | Orbit appears in | What it is |
|---|---|---|
| Install `orbit_store_ps4.pkg` with your package installer | **Games** on your PS4 | The TV app, used with your controller. [Install it](#install-the-native-tv-app). |
| Send `orbit_store.elf` to an ELF loader | **Internet Browser** on your PS4 | Opens Orbit in the PS4's browser. Keep Orbit's download service running on the PS4 to use it. [Set it up](#use-the-browser-version). |
| Install [Orbit Zero](orbit-zero.md) | Your Mac, Windows or Linux computer | Downloads on your computer and sends the files to your PS4. The PS4 doesn't need internet. Needs Orbit Store 0.0.2 or later on the PS4. |

The Games and browser versions share the same downloads, favourites and service settings, so seeing two Orbit entries on your PS4 is normal. Appearance is saved separately in each app or browser.

**Prefer downloading on your computer?** [Orbit Zero](orbit-zero.md) is our desktop app for Mac, Windows and Linux. It starts Orbit on your PS4, downloads on your computer and sends the files over your home network. Vikingfile and AkiraBox pages open on the computer, where their check usually passes in seconds. See [Install Orbit Zero](orbit-zero-installation.md).

## What you need

- A PS4 running a homebrew-capable jailbreak (for example GoldHEN). Orbit brings its own ELF loader (**elfldr**); to let Orbit start it, turn on GoldHEN's payload loader once: **GoldHEN → Servers Settings → Enable PayLoader Server**.
- A package installer for the TV app (for example GoldHEN's **Debug Settings → Package Installer**).
- Internet access on the console for direct provider downloads. With Orbit Zero, the computer downloads instead.
- Enough writable storage.
- A phone or computer on the same local network, if you want to control Orbit from one.

The current PS4 release is **Orbit Store 0.2.0**: **native app 0.2.0** with **download service 0.2.0**, plus **Orbit Zero 1.9.7** for your computer.

The instructions below use the default Store layout. If you choose another interface, check its settings entry under Appearance.

## Which files to download

Choose the app you use; you do not need to download every asset.

| How you use Orbit | What to download |
| --- | --- |
| Native PS4 app | **`orbit_store_ps4.pkg`** and its checksum. Native app **0.2.0** already includes service **0.2.0** and elfldr. The app starts the service itself; nothing has to run first. |
| Service started separately through an ELF loader | **`orbit_store.elf`** and its checksum. Send it once to an ELF loader on port 9021; Orbit then keeps its own copies current. |
| Orbit Zero | The `Orbit-Zero-1.9.7-*` package for your computer. Zero gets Orbit for PS4 from the release and starts it with **Start Orbit on PS4**, so you don't need to download the ELF. The TV app is optional if you also want TV controls. |

Installing a package or uploading an ELF does not replace an older service that is already running. Stop it with **Stop Orbit to restart** before starting the updated copy. In **Diagnostics & about**, the current versions are **native app 0.0.3** and **download service 0.0.3**. Later releases may update one without the other, so the two numbers can differ. Keep your pairing, settings and queue in place.

## Verify the PS4 files

Download the ELF or PKG and its matching `.sha256` file from the **same release**. Keep both files in one folder and open a terminal there. Run the command for the file you downloaded:

| System | ELF | Native PKG |
| --- | --- | --- |
| macOS | `shasum -a 256 -c orbit_store.elf.sha256` | `shasum -a 256 -c orbit_store_ps4.pkg.sha256` |
| Linux | `sha256sum -c orbit_store.elf.sha256` | `sha256sum -c orbit_store_ps4.pkg.sha256` |
| Windows PowerShell | `Get-FileHash .\orbit_store.elf -Algorithm SHA256` | `Get-FileHash .\orbit_store_ps4.pkg -Algorithm SHA256` |

On macOS or Linux, the result should say **OK**. On Windows, open the `.sha256` file in a text editor and compare its 64-character checksum with PowerShell's **Hash** value; uppercase and lowercase letters are equivalent. If it differs, download the file again before loading it.

Orbit Zero's packages use **`SHA256SUMS`** instead. See [Verify your download](orbit-zero-installation.md#verify-your-download).

## Install the native TV app

The native package includes Orbit's download service and **elfldr**, the ELF loader Orbit runs through. Nothing has to run first: when no ELF loader answers, the app gives its elfldr to GoldHEN's payload loader, then starts Orbit through it. Turn that loader on once in **GoldHEN → Servers Settings → Enable PayLoader Server**.

Close other apps such as ezRemote before opening Orbit. Programs started this way share memory with open apps, and with ezRemote open Orbit may not start. If Orbit doesn't answer, the app sends it once more, then shows **Orbit didn't start** with **Try again**. Right after the PS4 turns on, Orbit sometimes needs a second try to start, so the first start can take up to about 40 seconds longer.

1. Get `orbit_store_ps4.pkg` and `orbit_store_ps4.pkg.sha256` from the [latest release](https://github.com/saawant12/orbit-store-ps4/releases/latest), then [verify the checksum](#verify-the-ps4-files).
2. If an older Orbit service is running, stop it from **App settings → Updates & startup → Stop Orbit to restart** in the browser version. Installing a package does not replace a running service.
3. Copy the PKG to your PS4 on a USB drive (or over FTP), then install it with your jailbreak's package installer — for example **Settings → Debug Settings → Package Installer** under GoldHEN.
4. Open **Orbit Store** from the **Games row**. Discover is the starting page. On first use, select **Choose sources**, enable the sources you want and acknowledge the notice. Saving opens Discover. Source choices are shared with the browser.
5. Choose a game, source, format and destination drive. The [downloads guide](downloads.md) covers direct downloads and each provider's browser steps.

Already using Orbit? In the browser version, open **App settings → Updates & startup → TV app → Install on this PS4**. Orbit downloads the official package, verifies it and hands it to the console's package installer.

## Use the browser version

1. Get `orbit_store.elf` and `orbit_store.elf.sha256` from the [latest release](https://github.com/saawant12/orbit-store-ps4/releases/latest), then [verify the checksum](#verify-the-ps4-files).
2. Send the ELF to an ELF loader on port 9021 (for example elfldr, which GoldHEN's LaunchPad can start). GoldHEN's own loader and LaunchPad can't run `orbit_store.elf` itself; it is too big for them. Orbit saves its service and elfldr, and creates the **Orbit Store Browser** icon.
3. Open **Orbit Store Browser**, then **App settings → Sources & accounts**. Choose the sources you want to use, including Archive.org, Vikingfile and AkiraBox, and acknowledge the notice. Only download material you have permission to obtain and use.

![Orbit Store 0.0.1 download sources and notice in the PS4 TV app](../assets/0.0.1/store-sources.jpg)

*Sources are your choice. Turning one off later hides its options and pauses unfinished downloads without deleting files.*

Both interfaces use the same service, catalogue, favourites and download queue. The TV app does not need a pairing code on the console. The native app and browser use the same settings categories. Connections, retries and shutdown are under **Downloads**; destinations and cleanup are under **Storage & cleanup**. Accounts are under **Sources & accounts**, pairing is under **Devices**, and reports are under **Diagnostics & about**. Native's **Updates & startup** links to the browser for payload-manager and auto-start setup.

You can also get Orbit through a payload manager's source list; see the [optional payload manager feed](#optional-payload-manager-feed).

## Set up Orbit

### Choose a default drive

Open **App settings → Storage & cleanup** in the native app or browser. Select an available drive, or **Choose automatically** to let Orbit suggest a destination. For a new download, Orbit keeps your preferred drive while it has enough room; otherwise it suggests the suitable drive with the most projected space. Choosing another drive for a download also makes it the default. An explicit selection is not silently changed, and an existing download stays on its original drive. Review **Save to** before starting.

A drive connected to your phone or computer is not a PS4 destination. Attach your external drive to the console; Orbit uses its `homebrew` folder when available.

### Choose your language

Orbit Store and Orbit Zero support **26 interface languages**: English, Arabic, Czech, Danish, Dutch, Finnish, French, German, Greek, Hungarian, Indonesian, Italian, Japanese, Korean, Norwegian Bokmål, Polish, Portuguese (Brazil), Portuguese (Portugal), Romanian, Russian, Spanish, Swedish, Turkish, Ukrainian, Simplified Chinese and Traditional Chinese.

Open **Settings → Appearance → Language** (called **App settings** in Orbit Store's default layout). Choose a language or follow the system/browser language. Language choices stay on that device. Arabic uses a mirrored layout; Japanese, Chinese and Korean use fonts with their character sets. Changing the interface language does not change game or provider-page languages.

![Orbit Store 0.0.1 appearance and language settings in the PS4 TV app](../assets/0.0.1/store-language.jpg)

*Game names, descriptions and provider pages may keep their original language. Changing Orbit’s language does not change a downloaded game’s language.*


### Choose your interface

Choose **Store**, **Crossbar**, **Cinema** or **Panorama** in **App settings → Appearance** in native Store, or **Settings → Appearance** in the other native layouts. In the browser, use **App settings → Appearance** in Store or **Settings → Appearance** in another layout. In Orbit Zero, use the palette-shaped **Appearance** button in Store’s top bar, or **Settings → Appearance** in another layout.

Select **Keep** within 15 seconds to save your choice, or let the countdown return you to the previous interface. Downloads and favourites stay with you; the appearance choice is separate for each app or browser. The appearance settings also cover navigation, motion and the background. See [Appearance](appearance.md).

### Connect optional accounts

**TorBox:** to use optional TorBox downloads, connect your account in the browser's **App settings → Sources & accounts → TorBox**. Both apps can then use it for supported options. See [TorBox](downloads.md#torbox).

**Archive.org:** for account-required Archive.org files, open **App settings → Sources & accounts → Archive.org** in either app and sign in. See [Archive.org sign-in](downloads.md#archiveorg-sign-in).

Orbit Zero has its own TorBox, Archive.org and Vikingfile sign-ins on the computer, under **Settings → Sources & accounts**.

## Games and DLC

The catalogue has **1,739 PS4 games** with **1,856 download options** from Archive.org, Vikingfile and AkiraBox.

Downloading a PKG or FPKG saves a package to your selected drive. Choose **Install on PS4** on the finished download to hand it to the console's package installer. See [installing games](install-games.md).

**DLC is available.** Open **Add-ons** or **Add-ons (count)** on a game's details to browse expansions, content packs, activation packages and bundles. Check the required base game before downloading or installing. See [the DLC guide](add-ons.md).

## Pair your phone or computer

In the TV app, open **App settings → Devices** to see the console address and six-digit code. While Orbit is running, visit `http://<ps4-ip>:34177/` on the same network. Choose **Pair devices** and enter the six-digit code shown on the PS4. On the console, **Pair devices** keeps the code visible; **Show code on PS4** repeats its notification. Do not share the code publicly.

Your paired device controls the console's queue. For Vikingfile browser verification, use the PS4 screen to complete the provider steps even when you start from your phone.

### Use Orbit Zero on your computer

Orbit Zero for Mac, Windows and Linux (it needs Orbit Store 0.0.2 or later on your PS4) downloads games on your computer and sends them to your PS4, opens Vikingfile and AkiraBox pages on the computer so there’s no Cloudflare wait, and can start Orbit for you. See [Install Orbit Zero](orbit-zero-installation.md) and [Orbit Zero for PS4](orbit-zero.md).

### Use a local hostname

Orbit Store also accepts browser addresses whose hostname ends in `.home.arpa`, `.local` or `.localhost`, with the usual port `34177`. For example, if your home network already resolves `ps4.home.arpa` to your console, open `http://ps4.home.arpa:34177/`. Pairing works the same way as with the IP address.

Orbit does not create or advertise these names. Your router or local name service must resolve the hostname to the correct device. `.localhost` normally resolves to the device you are browsing on, so it is generally for local testing rather than a remote PS4. If a name does not resolve, use `http://<ps4-ip>:34177/`.

## Payload manager and auto-start

### Optional payload manager feed

In a payload manager that supports custom sources, add:

```text
https://raw.githubusercontent.com/saawant12/orbit-store-ps4/main/payloads.json
```

The feed lists the release's `orbit_store.elf` with its version and checksum. The full ELF only runs through an ELF loader on port 9021; GoldHEN's LaunchPad can't run it. To start Orbit from LaunchPad, use **Add Orbit** below instead.

### Keep a manager copy up to date

Open **App settings → Updates & startup → Payload managers** and choose **Add Orbit**, or **Allow updates to this copy** if it is already listed. That manager's copy then receives Orbit updates. The copy Orbit places is a small starter, not the service: it starts the service Orbit saved, starting elfldr through GoldHEN first when needed. **Stop syncing** leaves the existing copy and auto-start choices in place.

GoldHEN 2.4b18.10+ supports optional AutoRun. In Orbit, first allow a managed payload copy, then explicitly enable AutoRun. Orbit preserves unrelated entries in `payloads.ini`. AutoRun runs Orbit's starter after GoldHEN starts; it does not replace running the jailbreak after a reboot.

If you select **Stop syncing**, future Orbit updates leave that manager copy alone. It still starts the service Orbit saved, which Orbit's updates keep current.

## Update Orbit

*App updates install features and fixes. Refresh catalogue updates game data without reinstalling the app.*

### One-step updates

**Update Orbit** is under **Updates & startup**. It updates the TV app and download service together.

Orbit downloads only the package when it already includes the newest service. When the installation finishes, select **Close and reopen**. Reopen Orbit from the Games row. The updated app saves your queue, stops the older service and starts its new bundled service through elfldr. Downloads interrupted by that service restart continue. Check the running versions in **Diagnostics & about**.

For browser or service-only updates, **Restart Orbit** starts the saved service through elfldr, starting elfldr through GoldHEN's payload loader first when needed. If neither is available, follow Orbit's manual stop/start instructions.

In the native app, open **App settings → Updates & startup**. In the browser's Store layout, open **App settings → Updates & startup**; other browser layouts use **Settings → Updates & startup**.

### Update the download service

The separate controls below are useful for manual updates.

In the native app, open **App settings → Updates & startup → Download service**. Check for updates, install the chosen release, then confirm **Restart download service**. The app stops only Orbit and starts its saved service through elfldr. If no loader can be reached, follow the on-screen instructions to start Orbit manually.

The following steps apply to the browser version. The download service and native TV app have separate version numbers; compare the versions shown in their update panels.

1. Open **App settings → Updates & startup → Check for updates**.
2. Choose **Install update**, or **Reinstall release** for the current version. Orbit verifies the release checksum and saves the replacement.
3. Select **Stop Orbit to restart** and confirm. The queue is saved; other payloads are left running.
4. Start Orbit again: open the TV app, run Orbit from LaunchPad or Homebrew Launcher, or send `/data/orbit-store/orbit_store.elf` to your ELF loader. Reopen Orbit and resume any paused downloads.

The update panel shows three separate versions: **Running**, **Saved for next start** and **Latest release**. Uploading a new ELF while Orbit is running saves it for the next start; it does not change the service that is running now. If you copied Orbit into a manager yourself and it isn't kept in sync, replace that copy yourself. Keep the Orbit icon and saved data.

### Update the TV app

**Update Orbit** updates the TV app and service together; see [one-step updates](#one-step-updates). The following separate controls are useful when updating only the TV app.

In the native app, open **App settings → Updates & startup → TV app**, check for updates and choose **Update TV app**. Confirm **Replace with this release** if the package was installed manually. After installation, close and reopen the app.

Alternatively, use the browser:

1. Close the TV app using **PS button → Close Application**.
2. In the browser version, open **App settings → Updates & startup → TV app** and check for an update. Confirm replacement if you previously installed the package yourself. Orbit verifies the download and hands it to the console's package installer. If it cannot identify a safe installation to replace, follow the message instead of installing again.
3. Reopen Orbit from the Games row. If the console still opens the previous app, restart the console when convenient and run your jailbreak again.

If Orbit reports an unconfirmed install, use **Check** to recover the existing task; do not submit the package again. A saved update is not proof that the new native app is running. Close and reopen the app, then compare the running native version with the installed version. You can also install the package yourself with the console's package installer. The TV app's title ID is `ORBT00002`. Keep `/data/orbit-store/`; it holds your settings and queue.

The TV app includes a copy of the service. For a manual replacement or an older updater, stop the old service before starting the new copy. After an in-app update, choosing **Close and reopen** lets the updated app handle that service replacement when you open it again. If the saved service is newer than the one inside the TV app, opening the app keeps the newer one.
