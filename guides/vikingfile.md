# Use a Vikingfile account

**For Orbit Store 0.2.0 for PS4.**

Vikingfile identifies an account with an **account hash**: the private code it gives you instead of an email and password. Treat it like a password and don’t include it in issues, screenshots or diagnostic reports.

## Sign in

There are two ways to sign in on your PS4: on Vikingfile's page on your PS4 (below), or with a [pass from another device](#use-a-pass-from-another-device) when that page doesn't work on your PS4. Orbit Zero on a computer has [its own sign-in](#on-your-computer).

In the TV app, open **App settings → Sources & accounts** and scroll to **Vikingfile**. In the browser, open **App settings → Sources & accounts → Vikingfile** (or **Settings → Sources & accounts → Vikingfile** in Crossbar, Cinema and Panorama). Choose **Open Vikingfile account**. On Vikingfile’s official page, enter your account code, complete verification if asked and select **Login**. Return to Orbit and choose **Check sign-in**.

![Vikingfile settings in the PS4 TV app with Open Vikingfile account and Check sign-in](../assets/0.0.1/native-vikingfile-account.jpg)

*Vikingfile settings in the PS4 TV app, before the sign-in is confirmed. No account code is shown.*

Orbit shows **Signed in** only after Vikingfile confirms the session. Opening the page alone doesn’t count. To manage the account or sign out, reopen the same account page. The browser version and the TV app keep separate browser sessions, so you may need to sign in once in each one you use.

Orbit uses the active PS4 user’s Vikingfile session when it asks for, checks, downloads and resumes a file. These cookies aren’t stored in download history, shown in diagnostics or sent to TorBox or unrelated sites.

## Use a pass from another device

**Needs Orbit Store 0.0.2 or later.**

On some PS4s, Vikingfile's sign-in page freezes or closes during its verification. You can sign in on another device instead and give Orbit that sign-in, called a *pass*. Vikingfile stores it in your browser as a cookie named `PHPSESSID`.

1. On a computer, open vikingfile.com in Chrome, Edge, Firefox or Safari and sign in with your account code.
2. Open the browser's developer tools: press F12, or ⌥⌘I on a Mac. In Safari, first turn on **Settings → Advanced → Show features for web developers**.
3. Find the cookies: **Application → Cookies** in Chrome and Edge, or **Storage → Cookies** in Firefox and Safari. Select vikingfile.com.
4. Copy the **Value** of `PHPSESSID`.
5. Open Orbit in a browser on your computer or phone and go to the Vikingfile settings. Paste the value into **Sign-in pass (PHPSESSID)** and choose **Save pass**.

Phone browsers don't show cookies unless you add a cookie viewer, so copying the pass is easiest on a computer. You can paste it from any device.

Orbit checks the pass with Vikingfile before saving it and shows **Pass saved and signed in**. The pass is kept only on your PS4 and never shown again. Treat it like a password.

Orbit tries the pass first for Vikingfile downloads. If Vikingfile has ended it, Orbit uses the PS4's own sign-in, if any, and the settings say **Vikingfile has signed this pass out**. Copy a new one the same way. Signing out on vikingfile.com in that browser also ends the pass, so close the tab instead.

To remove the pass, choose **Forget pass** in the Vikingfile settings, in the browser version or the TV app.

## On your computer

In [Orbit Zero](orbit-zero.md), open **Settings → Sources & accounts → Vikingfile**, enter your account code and choose **Sign in**. Zero fills in the account field on Vikingfile’s official page. Complete any verification there. Zero clears the account field after submitting, and the sign-in stays on that computer. Use **Check sign-in** or **Sign out** in the same settings.

The computer’s sign-in and the PS4’s are separate. Pairing doesn’t copy either one to the other. With Orbit Zero, Vikingfile pages open on the computer, so you don’t need the PS4’s sign-in page at all.

## Downloading after sign-in

For a Vikingfile game, choose a drive and select **Download to PS4**. Orbit first asks Vikingfile for the file using your session. If Vikingfile returns a ready link, the download starts without opening the provider page.

If Vikingfile asks for verification, its page opens full screen. Complete the verification, move the pointer to **Download** with the left stick and press ○. ✕ does nothing on this page, so a stray press can’t close it and lose the verification. Orbit catches the ready link and returns to the app. To give up, press the PS button, return to Orbit and cancel the download page there.

Premium features are controlled by Vikingfile. **Signed in** doesn’t mean the account is Premium or that every file skips verification. Expired sessions and provider checks fall back to the provider page; sign in again if needed. Free accounts still work.

[Downloads](downloads.md) · [Settings](settings.md) · [Orbit Zero](orbit-zero.md) · [Troubleshooting](troubleshooting.md)
