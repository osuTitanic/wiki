# Установка

[TOC]

Чтобы начать играть, проследуйте на [страницу загрузки](https://osu.titanic.sh/download/) и выберите любой из предоставленных клиентов игры (от 2007 до 2015 года).

![BuildDownload](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/BuildDownload.png)

После завершения загрузки, распакуйте архив и запустите исполняемый файл `osu!.exe`.

(Возможно, что защитник Windows заблокирует загрузку клиента, это вызвано незарегистрированным сертификатом.)

## Регистрация аккаунта

Для регистрации аккаунта, перейдите на [страницу регистрации](https://osu.titanic.sh/account/register) или на главной странице нажмите кнопку "I'm New!". (**Учтите: вы можете иметь только *ОДИН* аккаунт!**)

![NewUser](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/NewUser.png)

После создания аккаунта, на указанную при регистрации почту придёт письмо для потверждения регистрации:

![Verification](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/Verification.png)

## Discord Bot

На [Discord-сервере](https://discord.gg/3VeNPgDUrK) проекта, для получения дополнительных возможностей, связанных с аккаунтом, вы можете привязать свой аккаунт с помощью бота, для этого в чате Discord-сервера введите '!link <имя аккаунта>' (без значков <>). После этого внутри игры вы получите сообщение от бота с кодом, который вы должны ввести в чате Discord-сервера в ответ на сообщение Discord-бота.

![Link-Start](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/Link-Start.png)

![Link-ingame](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/Link-ingame.png)

![Link-Finished](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/Link-Finished.png)

## Установка на Linux

### Шаг 1: Подготовка

**Установка git**

Ubuntu/Debian: `sudo apt install -y git`                                                                                                                   
Arch Linux: `sudo pacman -Sy --needed  --noconfirm git`                                                                                                    
Fedora: `sudo dnf install -y git`

**Установка Lutris**

Ubuntu/Debian: https://github.com/lutris/lutris/releases (Get the .deb package from here)
Arch Linux: `sudo pacman -S lutris`                                                                                                                        
Fedora: `sudo dnf install lutris`
Flatpak: `flatpak install flathub net.lutris.Lutris`

**Установка необходимых драйверов**

Вы можете обратиться к данному руководству:
https://github.com/lutris/docs/blob/master/InstallingDrivers.md

**Pipewire**

Pipewire работает с osu! лучше, чем Pulseaudio, вы можете установить его, используя данное руководство:
https://github.com/NelloKudo/osu-winello/wiki/Installing-PipeWire

### Шаг 2: Установка osu-winello

`git clone https://github.com/NelloKudo/osu-winello.git`                                                                                                       
`cd osu-winello`                                                                                                                                          
`chmod +x ./osu-winello.sh`                                                                                                                               
`./osu-winello.sh`                                                                                                                                        

### Шаг 3: Скачивание клиента

Скачайте любой клиент со [страницы загрузки](https://osu.titanic.sh/download/)

![image](https://github.com/user-attachments/assets/1651b93b-14df-413a-84e8-5aea72453f69)

### Шаг 4: Установка твиков в Lutris

`osu-wine --lutris` скопирует необходимые файлы и твики для Lutrus.
Введите 'y' и нажмите Enter. Это добавит osu!stable в библиотеку Lutris. Поскольку мы не устанавливаем osu!stable, инструкции ниже помогут установить клиент Titanic в Lutris

### Step 5: Install Titanic through Lutris

Unzip the .zip file downloaded from the Titanic site, you will get your osu! installation.

Secondly open Lutris and let it load fully for first startup

Then click the plus icon on top left. Then "Add locally installed game".
Give it a proper name and such. Set the runner to Wine.

![Screenshot_20240725_133107](https://github.com/user-attachments/assets/376a2733-b53d-459d-975e-6a0191c13c9b)

![Screenshot_20240725_133325](https://github.com/user-attachments/assets/204cec89-e219-4b7e-8df1-9c1b1b4fc362)


In Game options
Set the executable to the osu.exe inside of the zip you extracted.
Set working directory to the osu! folder of the zip you extracted.
Set the wine prefix to: /$HOME/.local/share/wineprefixes/osu-wineprefix

![image](https://github.com/user-attachments/assets/2cb08e7b-e99a-4557-8e1f-0a4df245e6c7)

![image](https://github.com/user-attachments/assets/cbd17b4e-d8f2-47fc-96f5-e27df50a9941)


In Runner options, 
Set wine-osu as the Wine version
![image](https://github.com/user-attachments/assets/4c89f660-0170-4e80-97f6-fc332f45a74a)

Turn off DXVK and VKD3D
![image](https://github.com/user-attachments/assets/e6e2fb21-47a6-49f4-b038-5bf6a667696c)


Make sure ESync and FSync are enabled 
Disable AMD FSR
Disable BattlEye Anticheat
Disable Easy Anticheat

![image](https://github.com/user-attachments/assets/b3b4e8ff-7ef5-40a2-bb26-b1106159eaea)


In System options,
Turn on advanced then click enable "disable Desktop effects"
![image](https://github.com/user-attachments/assets/372564d8-9977-433b-8cb2-663f1c0b8a1a)

Enable Feral Gamemode
![image](https://github.com/user-attachments/assets/d88718f4-580a-41eb-88dd-dc7f74fdc9d4)


Scroll down until you see Environment Variables
Click add
On the left side put WINE_BLOCK_GET_VERSION
On the right side put 1

This is what it should look like.
![image](https://github.com/user-attachments/assets/f5da68e2-2395-44f0-ab23-474798cc8287)


Now from here you can launch osu! and enjoy!

Для синхронизации задержки звука с Windows, в настройках osu! выставьте задержку звука (оффсет) на '-25 ms' или '-40 ms'

**Примечание для пользователей Wayland**

Вам, возможно, нужно будет применить твики, упомянутые здесь:
https://github.com/NelloKudo/osu-winello/wiki/Wayland-support

**Устранение неописанных проблем**

Если вы столкнулись с проблемами, решение которых не описано здесь, вы можете обратиться за помощью в [Discord-сервере проекта](https://discord.gg/qupv72e7YH) или на [подразделе форума](https://osu.titanic.sh/forum/7).
