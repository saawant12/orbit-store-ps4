# Set up Orbit on a PS4 without internet

Use **Orbit Zero on your computer** to start Orbit on your PS4 over your home network. Your computer handles online downloads and sends the files to the PS4. **The PS4 can keep its internet access blocked throughout setup and use.**

This guide covers **Orbit Zero 1.9.7** with **Orbit Store for PS4 0.0.2** or later. Get Orbit Zero from the [latest release](https://github.com/saawant12/orbit-store-ps4/releases/latest) and follow [Install Orbit Zero](orbit-zero-installation.md) first.

## What you need

- A Mac, Windows or Linux computer with Orbit Zero installed and internet access.
- A PS4 with **GoldHEN running** and its payload loader turned on once in **GoldHEN → Servers Settings → Enable PayLoader Server**. Orbit Zero doesn’t jailbreak the PS4.
- Both devices on the same home network, over **Wi-Fi or Ethernet**, or one of each.
- Enough free space on the computer for each download and on the PS4 drive you’ll use.

You don’t need to download anything on the PS4. Orbit Zero includes elfldr, gets Orbit for PS4 from GitHub on the computer and sends both over your home network.

## 1. Keep the PS4 on your home network

Leave the PS4 connected to your router by Wi-Fi or Ethernet. Keep your internet-blocking setup in place, as long as devices on your home network can still reach each other.

**Don’t disconnect the PS4 from Wi-Fi or unplug its network cable.** Blocking internet access and leaving the network are different things. Avoid guest Wi-Fi or client isolation, which stop the computer and the PS4 from reaching each other.

Find the PS4’s IP address in **Settings → Network → View Connection Status**. An internet connection test can fail while your home network still works.

When your computer asks, allow Orbit Zero on the local network or through its firewall. See [macOS](orbit-zero-installation.md#macos), [Windows](orbit-zero-installation.md#windows) or [Linux](orbit-zero-installation.md#ubuntu-and-debian). You don’t need to open ports on your router.

## 2. Start Orbit from the computer

1. Start GoldHEN on your PS4.
2. In Orbit Zero, open **Settings → Updates & startup**.
3. Enter your **PS4’s IP address** and choose **PS4**. Leave **Orbit port** at **34177** unless you changed it.
4. Select **Start Orbit on PS4** and wait. Orbit Zero connects by itself afterwards.

Zero gets Orbit for PS4 from GitHub on the computer, checks it and sends it to the ELF loader on port 9021. If no ELF loader is running, Zero first sends its included elfldr to GoldHEN’s payload loader on port 9090. Everything reaches the PS4 over your home network; the PS4 doesn’t visit GitHub or any download site.

If Orbit is already running, select **Connect to Orbit** in **Settings → Devices** instead. If Orbit doesn’t start, close other homebrew apps such as ezRemote, then try again.

To send an ELF you downloaded yourself, download `orbit_store.elf` from the [release](https://github.com/saawant12/orbit-store-ps4/releases/latest) on the computer, check its `.sha256`, then choose it under **Start Orbit on PS4 → Advanced → Choose another ELF** and select **Send custom ELF**.

## 3. Pair the computer and the PS4

1. When Orbit Zero shows **Pairing required**, open **Settings → Devices** and select **Show code on PS4**.
2. Read the six-digit code in the PS4 notification.
3. Enter it in Orbit Zero and select **Pair with PS4**.
4. If your computer asks to unlock its credential store, allow Orbit Zero to save the pairing. Enter a computer password only in the operating system’s own prompt.

If you miss the notification, ask for the code again after the countdown. Pairing happens on your home network and doesn’t need internet on the PS4.

## 4. Download through the computer

Once **Connected** appears, check that your PS4 drive is listed in **Console**, and that **Settings → Downloads → Download preference** is **Computer**.

Open a game, choose its source and a PS4 drive, then start the download. **Downloads** shows each step:

- **Download to computer:** progress and speed from the download site.
- **Extract on computer:** for ZIP, RAR and 7z downloads. Keep room for the archive and its extracted files.
- **Transfer to PS4:** progress and speed over your home network.

For Vikingfile and AkiraBox, the page opens **on the computer**, where its check usually passes in seconds. Complete any check that stays, then wait without pressing **Download**: Zero catches the ready link and closes the page.

When the transfer finishes, select **Install on PS4**. The installer uses the file already on the PS4, so no internet is needed. Installing doesn’t change a game’s own online requirements.

Keep **both devices awake** and Orbit Zero open until the transfer finishes. The computer keeps its copy by default; change that in **Settings → Storage & cleanup → Computer cache**.

The **Computer** preference only chooses where downloads run. It doesn’t change your router or block the PS4’s internet access for you.

## Optional: the TV app on your PS4

You can do everything from the computer. To browse and control the computer’s downloads from your TV, install the TV app from a USB drive:

1. On the **computer**, download `orbit_store_ps4.pkg` and its `.sha256` from the [release](https://github.com/saawant12/orbit-store-ps4/releases/latest) and check the checksum. See [Getting started](getting-started.md).
2. Copy the PKG to a USB drive and plug it into the PS4.
3. Install it with GoldHEN’s **Settings → Debug Settings → Package Installer**, then open **Orbit Store** from the Games row.
4. In the TV app, open **App settings → Devices** and select **Enable Orbit Zero**. Pair the computer first if the app says no computer is paired.

New downloads then follow the **Computer** preference set on the computer. Keep Orbit Zero open; Vikingfile and AkiraBox checks happen on the computer.

To update the TV app on a PS4 without internet, install the newer PKG the same way. Orbit’s settings and queue in `/data/orbit-store/` stay.

## Next time you use it

1. After the PS4 restarts, start GoldHEN again.
2. Open Orbit Zero. If Orbit isn’t running, use **Start Orbit on PS4**, or open the TV app. Zero reconnects by itself when the PS4 is reachable; otherwise select **Reconnect**.
3. The saved pairing is used again. Select **Resume** for downloads that were paused or interrupted.

If the PS4’s address or pairing changes, see [Reconnect after an address change](orbit-zero.md#reconnect-after-an-address-change).

## Troubleshooting

| What you see | What to check |
| --- | --- |
| The PS4 says it has no internet | That’s expected with internet blocked. Check that Orbit Zero can reach the PS4’s IP address. |
| “Neither an ELF loader nor GoldHEN’s payload loader answered” | Start GoldHEN and turn on **Enable PayLoader Server**. |
| “elfldr was sent, but no ELF loader started” | Close other homebrew apps such as ezRemote, then try again. |
| “Could not get Orbit for PS4 from GitHub” | The computer needs internet for this step. Or download `orbit_store.elf` yourself and use **Choose another ELF**. |
| Orbit can’t be reached on 34177 | Start Orbit, check the PS4’s current IP and allow local network access on the computer. |
| No pairing code appeared | Select **Show code on PS4** and watch for the PS4 notification. |
| The TV app can’t find the computer | Keep Zero open, pair it first, select **Enable Orbit Zero**, and check that the computer’s firewall allows local access. |
| A transfer stopped after sleep or a disconnect | Wake both devices, reconnect the same PS4 and select **Resume**. See [Pause, reconnect and clean up](orbit-zero.md#pause-reconnect-and-clean-up). |
