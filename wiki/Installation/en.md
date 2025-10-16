# Installation

[TOC]

To begin playing on Titanic! you can head over to the [Download page](https://osu.titanic.sh/download/) and pick any client from as old as 2007 up to 2015.

![BuildDownload](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/BuildDownload.png)

After it finishes installing, all you have to do is extract the folder and double-click `osu!.exe`.

There is a chance that Windows Defender may block it, since the game is unsigned (a certificate for that would cost 200$). An alternative would be to use the [[Patcher]], which is still experimental, but does not get blocked by Windows Defender from our testing.

## Registering an account

To register an account you can go to the [registration page](https://osu.titanic.sh/account/register) by clicking on "I'm New!" (**Remember you are only allowed to have *ONE* account EVER!**)

![NewUser](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/NewUser.png)

After you create your account you will be prompted to verify your email:

![Verification](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/Verification.png)

## Linux Installation

### Step 1: Prerequisites

**Install git**

Ubuntu/Debian: `sudo apt install -y git`                                                                                                                   
Arch Linux: `sudo pacman -Sy --needed  --noconfirm git`                                                                                                    
Fedora: `sudo dnf install -y git`

**Install Lutris**

Ubuntu/Debian: <https://github.com/lutris/lutris/releases> (Get the .deb package from here)  
Arch Linux: `sudo pacman -S lutris`  
Fedora: `sudo dnf install lutris`  
Flatpak: `flatpak install flathub net.lutris.Lutris` 

**Install graphics drivers**

If you haven't done so, you can refer to this guide:  
<https://github.com/lutris/docs/blob/master/InstallingDrivers.md>

**Pipewire**

Pipewire performs much better on osu! than Pulseaudio, you can install it by following this guide:  
<https://github.com/NelloKudo/osu-winello/wiki/Installing-PipeWire>

### Step 2: Installation of osu-winello

```
git clone https://github.com/NelloKudo/osu-winello.git
cd osu-winello
chmod +x ./osu-winello.sh
./osu-winello.sh
```

### Step 3: Download the Titanic client

You can download any version from [here](https://osu.titanic.sh/download/)

![BuildDownloadSmall](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/BuildDownloadSmall.png)

### Step 5: Install Titanic through Lutris

Unzip the .zip file downloaded from the Titanic site, you will get your osu! installation.  
Secondly open Lutris and let it load fully for first startup.  
Then click the plus icon on top left. Then "Add locally installed game".
Give it a proper name and such. Set the runner to Wine.

![LutrisAddLocalGame](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisAddLocalGame.png)

![LutrisGameInfo](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisGameInfo.png)


**In Game options:**

Set the executable to the osu.exe inside of the zip you extracted.  
Set working directory to the osu! folder of the zip you extracted.  
Set the wine prefix to `~/.local/share/wineprefixes/osu-wineprefix`.

![LutrisWineprefix](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisWineprefix.png)

![LutrisGameOptions](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisGameOptions.png)


**In Runner options:**
 
Set wine-osu as the Wine version:  
![LutrisWineVersion](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisWineVersion.png)

Turn off DXVK and VKD3D:  
![LutrisGraphicsSection](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisGraphicsSection.png)


Make sure ESync and FSync are enabled.
Additionally, disable AMD FSR, BattlEye Anti-Cheat and Easy Anti-Cheat.  
![LutrisEsyncFsync](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisEsyncFsync.png)


**In System options:**

Turn on "Advanced" mode then switch "Disable desktop effects" on:  
![LutrisDisableDesktopEffects](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisDisableDesktopEffects.png)

Enable Feral Gamemode:  
![LutrisFeralGamemode](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisFeralGamemode.png)


Scroll down until you see Environment Variables.  
Click add.  
On the left side put WINE_BLOCK_GET_VERSION.
On the right side put 1.

This is what it should look like:  
![LutrisEnvironment](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisEnvironment.png)


Now from here you can launch osu! and enjoy!

**NOTE:** Be sure to set the offset to around `-30` to `-20 ms` offset. Then the audio will be like Windows!

**Note for Wayland users**

You may have to apply the tweaks listed here:  
<https://github.com/NelloKudo/osu-winello/wiki/Wayland-support>

If you have any issues do not be afraid to ask in the [Titanic! Discord server](https://discord.gg/qupv72e7YH) or in the [support sub-forum](https://osu.titanic.sh/forum/7).
