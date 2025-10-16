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

## Discord Bot

If you want to use the bot on our [Discord server](https://discord.gg/3VeNPgDUrK), all you have to do is type `!link <username>` and you will be sent a verification code in-game.

![Link-Start](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/Link-Start.png)

![Link-ingame](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/Link-ingame.png)

![Link-Finished](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/Link-Finished.png)

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

**Install needed drivers**

You can refer to this guide:
<https://github.com/lutris/docs/blob/master/InstallingDrivers.md>

**Pipewire**

Pipewire performs much better on osu! than Pulseaudio, you can install it by following this guide:
<https://github.com/NelloKudo/osu-winello/wiki/Installing-PipeWire>

### Step 2: Installation of osu-winello

`git clone https://github.com/NelloKudo/osu-winello.git`  
`cd osu-winello`  
`chmod +x ./osu-winello.sh`  
`./osu-winello.sh`

### Step 3: Download the Titanic client

You can download any version from [here](https://osu.titanic.sh/download/)

![image](https://github.com/user-attachments/assets/1651b93b-14df-413a-84e8-5aea72453f69)

### Step 4: Installing the tweaks into Lutris

`osu-wine --lutris` command will copy the necessary files and tweaks for Lutris.  
Type `y` then hit enter. It will give instructions to add osu!stable to Lutris. Since we are not installing osu!stable, the below is how to install Titanic in Lutris.

### Step 5: Install Titanic through Lutris

Unzip the .zip file downloaded from the Titanic site, you will get your osu! installation.  
Secondly open Lutris and let it load fully for first startup.  
Then click the plus icon on top left. Then "Add locally installed game".
Give it a proper name and such. Set the runner to Wine.

![Screenshot_20240725_133107](https://github.com/user-attachments/assets/376a2733-b53d-459d-975e-6a0191c13c9b)

![Screenshot_20240725_133325](https://github.com/user-attachments/assets/204cec89-e219-4b7e-8df1-9c1b1b4fc362)


**In Game options:**

Set the executable to the osu.exe inside of the zip you extracted.  
Set working directory to the osu! folder of the zip you extracted.  
Set the wine prefix to `/$HOME/.local/share/wineprefixes/osu-wineprefix`.

![image](https://github.com/user-attachments/assets/2cb08e7b-e99a-4557-8e1f-0a4df245e6c7)

![image](https://github.com/user-attachments/assets/cbd17b4e-d8f2-47fc-96f5-e27df50a9941)


**In Runner options:**
 
Set wine-osu as the Wine version:  
![image](https://github.com/user-attachments/assets/4c89f660-0170-4e80-97f6-fc332f45a74a)

Turn off DXVK and VKD3D:  
![image](https://github.com/user-attachments/assets/e6e2fb21-47a6-49f4-b038-5bf6a667696c)


Make sure ESync and FSync are enabled.
Disable AMD FSR.
Disable BattlEye Anticheat.
Disable Easy Anticheat.  
![image](https://github.com/user-attachments/assets/b3b4e8ff-7ef5-40a2-bb26-b1106159eaea)


**In System options:**

Turn on "Advanced" mode then switch "Disable desktop effects" on:  
![image](https://github.com/user-attachments/assets/372564d8-9977-433b-8cb2-663f1c0b8a1a)

Enable Feral Gamemode:  
![image](https://github.com/user-attachments/assets/d88718f4-580a-41eb-88dd-dc7f74fdc9d4)


Scroll down until you see Environment Variables.  
Click add.  
On the left side put WINE_BLOCK_GET_VERSION.
On the right side put 1.

This is what it should look like:  
![image](https://github.com/user-attachments/assets/f5da68e2-2395-44f0-ab23-474798cc8287)


Now from here you can launch osu! and enjoy!

**NOTE:** Be sure to set the offset to around `-40` to `-25 ms` offset. Then the audio will be like Windows!

**Note for Wayland users**

You may have to apply the tweaks listed here:
<https://github.com/NelloKudo/osu-winello/wiki/Wayland-support>

If you have any issues do not be afraid to ask in the [Titanic! Discord server](https://discord.gg/qupv72e7YH) or in the [support sub-forum](https://osu.titanic.sh/forum/7).
