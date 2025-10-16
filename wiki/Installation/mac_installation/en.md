# Playing on macOS

This page is designed to help you run Titanic, if you are using a Macintosh computer.

## Prerequisites

For this guide you'll need the following things:

- A supported macintosh
- A client from the site
- The correct wineskin
    - [Fallback](https://cdn.titanic.sh/public/osx/osx-fallback.base.zip) - Used with clients from mid-2015 or earlier, or those marked as "fallback"
    - [Latest](https://cdn.titanic.sh/public/osx/osx-latest.base.zip) - Used with all clients after around mid-2015

Make sure your Mac is running a operating system above *High Sierra*, as it is required for the best performance and this guide. Although it might run on High Sierra, most browsers don't support GitHub.  
**For the best performance, please make sure your Mac is a 2011 or higher.** A 2008 or higher will run it, but 2011 or higher is recommended. It also has to support 32/64 bit capabillites.

## Installation

1. Make sure you have downloaded a client from the [downloads page](https://osu.titanic.sh/download/) and the correct *wineskin*, as outlined in the beginning of this document.
2. Once you have extracted both of them, head into the *osu!* application package by right-clicking and selecting *Show Package Contents*.
3. Now navigate to **drive_c -> osu!**. Here's the location where we're going to place the osu! client. Go back to your folder, where you extracted your desired client, copy every file thats inside, and paste it inside the **drive_c -> osu!** folder.
4. Double-click the now updated osu! application, and start clicking circles!

### Disabling System Integrity Protection (SIP)

**Important! If your Mac is running any Catalina version below `10.15.5`, you'll need to disable System Integrity Protection (SIP).**  
To disable SIP, do the following:

1. Restart your computer in Recovery mode.
2. Turn on your Mac and immediately press and hold these two keys: Command (⌘) and `R`.
3. Release the keys when you see an Apple logo, spinning globe or other startup screen.
4. You may be prompted to enter a password, such as a firmware password or the password of a user who is an administrator of this Mac. Enter the requested password to continue.
5. Launch Terminal from the Utilities menu. It should be in the menu bar at the top of your screen.
6. Run the command `csrutil disable`.
7. Restart your computer. You can do so from the top menu bar (just like you would normally.)
8. Once you have SIP disabled, let it boot up normally, login, and you can then begin to install osu!.

### Troubleshooting with osu!macOS Agent

If you encounter issues with the installation process, you might want to try the **osu!macOS Agent**, developed by [Technocoder](https://osu.ppy.sh/users/10338558). You can download it from the [macOS Installation Guide](https://osu.ppy.sh/community/forums/topics/1106057) forum post.

1. Open osu!macOS Agent
2. Select your osu! application package
3. Click on the *Troubleshoot* tab
4. Click the *Scan* button
5. Click the *Repair* button
6. Now restart osu! to see if your issue was fixed

There's still a good chance that it will not work. If that is the case, don't be afraid to ask for support in the [Titanic! Discord server](https://discord.gg/qryYG2C5nc) or in the [support sub-forum](https://osu.titanic.sh/forum/7).
