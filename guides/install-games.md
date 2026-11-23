# Install games without leaving Orbit

**For Orbit Store 0.2.0 for PS4.**

## Install a downloaded game

1. Finish downloading the game to your PS4. Orbit unpacks ZIP, RAR and 7z downloads first.
2. Open the finished entry in **Downloads** and choose **Downloaded files** or **Install on PS4**.
3. If it has several packages, choose the one you want to install.
4. Select **Install on PS4** and follow its installation status.

The same controls are in the TV app, the browser and Orbit Zero, in all four interfaces. Downloading and installing have separate progress: a finished download means the files are saved, not that the game is installed.

The PS4 installs to its own installation storage. Choosing a download drive doesn’t choose where the game installs. Allow space for both copies during installation. Downloaded PKG and FPKG files stay on the drive by default.

To delete a downloaded package after it installs, turn on **App settings → Storage & cleanup → Installed packages → Delete packages after installing**. It’s off by default. If installation fails or the file changed after it was checked, Orbit keeps it. Archive cleanup has its own setting.

Installation needs a jailbroken PS4 with GoldHEN. It doesn’t change a game’s firmware, licence or jailbreak requirements. Orbit doesn’t start games, and uninstalls one only when you choose it in [Free up space](downloads.md#free-up-space). If Orbit kept the package of a game you uninstalled there, **Install** is offered for it in **Downloads** again.

## Install from Files

Open **Library → Files**, select a PKG or FPKG file, and choose **Install on PS4**. See [Files](files.md).

## Install from Orbit Zero

In [Orbit Zero](orbit-zero.md), you can download to **This computer** without a connected PS4. When you’re ready, pair or reconnect your PS4 and choose **Send to PS4**. After the transfer finishes, choose **Install on PS4** in Downloads, or open **Downloaded files** and choose it there.

Installation runs on the PS4, not on your computer. Keep the PS4 awake and Orbit running on it. With Orbit Store 0.0.3 or later, **Stream & install** can instead install a finished computer download straight from the computer, without a copy on the PS4. See [Stream & install](orbit-zero.md#stream--install).

## Add-ons and bundles

Find DLC on **Add-ons**, or use **Add-ons (count)** from a game’s details. See [the DLC guide](add-ons.md) for the content types and download choices.

Review the required base-game edition, title ID and known version requirements before installing DLC. A matching title ID alone doesn’t confirm compatibility, and seeing the base game in Library doesn’t mean its DLC is installed.

For a bundle, select and install each package you want. Orbit doesn’t install the whole bundle automatically, fetch missing game updates or choose the installation order. [Get everything](downloads.md#get-everything) is different: it adds a game with its update and DLC and installs them in order, and Library’s [Updates](library.md#game-updates) installs updates by themselves. Activation packages need their content to already be in the base game.

## If installation needs attention

- **The button is missing:** the download must have finished on the PS4. Only PKG and FPKG files can be installed; game images and game folders aren’t supported on PS4.
- **The original drive is unavailable:** reconnect the drive that holds the downloaded file. Orbit keeps the download’s original location rather than picking a different copy.
- **The installer reports an error:** follow the message and check space, package compatibility and GoldHEN. The downloaded file is kept for another try.
- **The installer reports a conflict with an installed game:** Orbit keeps the installed game and your downloaded file and shows the error. It never uninstalls a game by itself.
- **Installation status is unconfirmed:** use **Check installation** when offered and check the PS4 home screen. Orbit doesn’t send an uncertain installation again by itself after a restart or a lost response.

For a report, include the Orbit version, the game or add-on, its format, the drive and the exact installation error. Keep the files while investigating.

[Downloads](downloads.md) · [Library](library.md) · [Troubleshooting](troubleshooting.md)
