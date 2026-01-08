# Installation

[TOC]

Pour commencer à jouer à Titanic!, vous pouvez aller sur la [page de téléchargement](https://osu.titanic.sh/download/) et choisir n'importe quel client, aussi vieux que 2007, jusqu'à 2015.

![BuildDownload](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/BuildDownload.png)

Après que cela ai fini de télécharger, tout ce que vous devez faire est extraire le fichier et double cliquer sur `osu.exe`.
Il y a une chance que Windows Defender le bloque, vu que le jeu n'est pas signé (un certificat coûterait $200). Une alternative serait d'utiliser le [[Patcheur]], qui est toujours expérimental, mais ne se fait pas bloquer par Windows Defender selon nos tests. (unsure)

## Créer un compte

Pour créer un compte vous pouvez aller sur la [page de création de compte](https://osu.titanic.sh/account/register) en cliquant sur ”I'm New!” (**Rappelez vous, vous êtes autorisé à avoir *UN* seul compte pour TOUJOURS!**)

![NewUser](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/NewUser.png)

Après avoir créer votre compte, vous recevrez une demande de vérification d'email:

![Verification](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/Verification.png)

## Installation sur Linux

### Prérequis

**Installer git**

Ubuntu/Debian: `sudo apt install -y git`                                                                                                                   
Arch Linux: `sudo pacman -Sy --needed  --noconfirm git`                                                                                                    
Fedora: `sudo dnf install -y git`

**Installer Lutris**

Ubuntu/Debian: <https://github.com/lutris/lutris/releases> (Prenez le package .deb depuis ici)  
.Arch Linux: `sudo pacman -S lutris`  
Fedora: `sudo dnf install lutris`  
Flatpak: `flatpak install flathub net.lutris.Lutris` 

**Installer les graphics drivers**

Si vous ne l'avez pas fait, vous pouvez vous référez à ce guide:  
<https://github.com/lutris/docs/blob/master/InstallingDrivers.md>

**Pipewire**

Pipewire performe bien mieux sur osu! que Pulseaudio, vous pouvez l'installer en suivant ce guide:  
<https://github.com/NelloKudo/osu-winello/wiki/Installing-PipeWire>

### Installation de osu-winello

[osu-winello](https://github.com/NelloKudo/osu-winello), développé par [NelloKudo](https://github.com/NelloKudo), est actuellement le meilleur moyen de faire tourner osu!stable sur Linux. Nous l'utiliserons pour lancer nos installations de Titanic plus tard.  
Suivez ces commandes pour le configurer:

```
git clone https://github.com/NelloKudo/osu-winello.git
cd osu-winello
chmod +x ./osu-winello.sh
./osu-winello.sh
```

### Téléchargez le client de Titanic.

Vous pouvez télécharger n'importe quelle version patchée de osu! depuis la [page de téléchargement](https://osu.titanic.sh/download/).

![BuildDownloadSmall](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/BuildDownloadSmall.png)

### Installer Titanic avec Lutris

Décompresser le fichier `.zip` téléchargé depuis Titanic pour avoir votre fichier d'installation
Ouvrez Lutris et laissez le charger complètement pour le premier lancement.
Puis appuyez sur l'icône plus en haut à gauche -> sélectionnez ”*Add locally installed game*”
Donnez lui un nom cohérent, et mettez le 'runner' sur *Wine*

![LutrisAddLocalGame](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisAddLocalGame.png)

![LutrisGameInfo](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisGameInfo.png)


**Options dans le jeu:**

Mettez l'exécutable du osu.exe dans le fichier zip que vous avez extrait.
Mettez le répertoire de travail dans le fichier zip du osu! que vous avez extrait.
Mettez le préfixe wine sur `~/.local/share/wineprefixes/osu-wineprefix`.

![LutrisWineprefix](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisWineprefix.png)

![LutrisGameOptions](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisGameOptions.png)


**Dans l'option 'Runner':**
 
Mettez `~/.local/share/osuconfig/yawl-winello` en tant que version Wine:  
![LutrisWineVersion](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisWineVersion.png)

Désactivez DXVK et VKD3D:  
![LutrisGraphicsSection](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisGraphicsSection.png)


Soyez sûre que ESync et FSync sont activés.
Additionnellement, désactivez AMD FSR, BattleEye Anti-Cheat et Easy Anti-Cheat.
![LutrisEsyncFsync](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisEsyncFsync.png)


**Dans les options du Système:**

Activez le mode ”Advanced” et puis activez aussi ”Disable desktop effects”:  
![LutrisDisableDesktopEffects](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisDisableDesktopEffects.png)

Activez le 'Gamemode Feral':  
![LutrisFeralGamemode](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisFeralGamemode.png)


Descendez jusqu'à ce que vous voyez 'Environment Variables'.
Appuyez sur 'add'
Sur la gauche, mettez WINE_BLOCK_GET_VERSION.
Sur la droite, mettez 1.

Ceci est ce à quoi cela devrait ressembler:  
![LutrisEnvironment](https://raw.githubusercontent.com/osuTitanic/wiki/refs/heads/main/wiki/Installation/img/LutrisEnvironment.png)


Maintenant, vous pouvez lancer osu! et vous amusez!

**NOTE:** Soyez sûre de mettre l'offset aux alentours de `-30`à `-20ms`. Comme cela, l'audio sera comme sur Windows!

**Note pour les utilisateurs de Wayland**

Si vous tournez sur wayland, vous devrez peut-être rajouter quelque ajustement listé ici:  
<https://github.com/NelloKudo/osu-winello/wiki/Wayland-support>

Si vous avez n'importe quel problème, n'ayez pas peur de demander dans le [Serveur Discord de Titanic!](https://discord.gg/qupv72e7YH) ou dans le [sous-fil de support](https://osu.titanic.sh/forum/7).

## Installation sur macOS

### Prérequis

Pour faire tourner Titanic! sur un ordinateur Macintosh, vous auriez besoin des choses suivante:

- Un macintosh supporté (2011 et après)
- Un client depuis la [page de téléchargement](https://osu.titanic.sh/download/)
- Le bon wineskin
    - [Fallback](https://cdn.titanic.sh/public/osx/osx-fallback.base.zip) - Utilisé avec les clients de mi-2015 ou avant, ou ceux marqué en tant que ”fallback”
    - [Latest](https://cdn.titanic.sh/public/osx/osx-latest.base.zip) - Utilisé avec tout les clients après mi-2015

Soyez sûre que votre Mac tourne sur un système d'opération supérieur à *High Sierra*, car cela est requis pour la meilleure performance et ce guide. Même si cela peut tourner sur High Sierra, la plupart des navigateurs ne supporte pas GitHub.
**Pour la meilleure performance, s'il vous plaît soyez sûre que le Mac est de 2011 ou après.** Un de 2008 pourrait le faire tourner, mais 2011 ou après est recommandé. Ceux-là ont aussi la capacité de supporter 32/64 bit.

### Installation
	
1. Soyez sûre que vous avez téléchargé un client depuis la [page de téléchargement](https://osu.titanic.sh/download/) et le bon *wineskin*, comme expliqué au début de ce document.
2. Dès que vous avez extrait les 2 fichiers, allez dans le package d'application *osu!* en faisant un clic droit et en choisissant *Afficher le contenu des Packages*.
3. Maintenant, allez sur **drive_c -> osu!**. Ici, vous trouverez la location où nous placerons le client osu!. Revenez sur votre fichier, ou vous allez extraire votre client désiré, copier tout les fichier qui sont à l'intérieur, et les coller dans le fichier **drive_c -> osu!**.
4. Double cliquez sur l'application osu! qui est maintenant à jour, et commencez à appuyer sur des cercles!

### Désactivez la Protection de l'Intégrité du Système (SIP)

**Important! Si votre Mac tourne sur n'importe quelle version de Catalina en dessous de `10.15.5`, vous devriez désactiver la Protection de l'Intégrité du Système (SIP)**
Pour désactiver l'SIP, suivez ces instructions:

1. Redémarrez votre ordinateur en mode Récupération.
2. Allumez votre Mac et appuyez immédiatement et restez appuyez sur ces deux touches: Command (⌘) et `R`.
3. Relachez les 2 touches quand vous voyez le logo Apple, un globe qui tourne, ou n'importe quelle autre écran de démarrage.
4. Vous serez peut être demander d'entrer un mot de passe, telle qu'un mot de passe de micrologiciel ou le mot de passe d'un utilisateur qui est administrateur de ce Mac
5. Lancez le *Terminal* depuis le menu utilitaire. Cela devrait être dans le menu bar tout en haut de votre écran.
6. Exécutez la commande `csrutil disable`.
7. Redémarrez votre ordinateur. Vous pouvez faire cela depuis le menu bar en haut, comme vous le feriez normalement.
8. Dès que la SIP est désactivée, laissez le s'allumer normalement, connectez vous, et vous pouvez maintenant installer osu!.

### Dépannage avec l'Agent osu!macOS

Si vous rencontrez des problèmes pendant l'installation, vous pouvez essayer l'**Agent osu!macOS**, développé par [Technocoder](https://osu.ppy.sh/users/10338558). Vous pouvez aussi le télécharger depuis le fil de discussion "[Guide d'Installation macOS](https://osu.ppy.sh/community/forums/topics/1106057)" (ceci est en Anglais).

1. Ouvrez l'Agent osu!macOS
2. Sélectionnez votre package de l'application osu!
3. Appuyez sur l'onglet *Troubleshoot*
5. Appuyez sur le bouton *Scan*
6. Maintenant redémarrez osu! pour voir si votre problème a été réparé.

Il y a quand même une grande chance que cela ne fonctionne pas. Si c'en est le cas, n'ayez pas peur de demander de l'aide dans le [serveur Discord de Titanic!](https://discord.gg/qryYG2C5nc) ou dans le [sous fil de support](https://osu.titanic.sh/forum/7).
