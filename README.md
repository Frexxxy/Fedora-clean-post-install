## Reqs
- installed Fedora KDE Desktop 
- internet

## Updates
### Software
```console
sudo dnf upgrade --refresh
sudo dnf distro-sync
sudo dnf autoremove
sudo dnf clean all
```

### Flatpak
```console
sudo flatpak update
sudo flatpak uninstall --unused
```

### Firmware
``` console
sudo fwupdmgr refresh --force
sudo fwupdmgr get-deevices
sudo fwupdmgr get-updates
sudo fwupdmgr update
```
## Uninstall Software
``` console
dnf remove firefox
```

## System settings
- System Settings / Global Design: Enable [Switch to dark mode at night]
- System Settings / Background image: Mountain
- System Settings / Night Light
-   Switching times: sunrise and sunset
-   Nighttime temperature: 3800K
- System Settings / Shortcuts:
-   Search for the "Konsole"
-   Change the "Start" shortcut to "Meta + T" 

## Install software
### Prereqs
``` console
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```

### DNF
``` console
sudo dnf install fuse
sudo dnf install evolution 
```

#### Configuration Evolution
1. Add Mail account
2. Add calendar account
3. Set alias "outlook"


### Flatpaks
``` console
sudo flatpak install flathub it.mijorus.gearlever
sudo flatpak install flathub io.github.CyberTimon.RapidRAW
sudo flatpak install flathub app.zen_browser.zen
sudo flatpak install flathub org.kde.kate
sudo flatpak install flathub md.obsidian.Obsidian
sudo flatpak install flathub org.keepassxc.KeePassXC
```

### KDrive
1. Download file from https://www.infomaniak.com/en/apps/download-kdrive
2. Install, Login

### Starship
#### Install Starship
``` console
curl -sS https://starship.rs/install.sh | sh
```

#### Install nerd font
https://github.com/ryanoasis/nerd-fonts/releases/download/v3.4.0/FiraCode.zip

#### Update config from bash
``` console
sudo nano ~/.bashrc
```
Add the following at the end:
``` console
eval "$(starship init bash)"
```

#### Update config from starship
``` console
sudo nano  ~/.config/starship.toml
```
Add the following:
``` 
"$schema" = 'https://starship.rs/config-schema.json'

format = """
[░▒▓](#a3aed2)\
[ · ](bg:#a3aed2 fg:#090c0c)\
[](bg:#769ff0 fg:#a3aed2)\
$directory\
[](fg:#769ff0 bg:#394260)\
$git_branch\
$git_status\
[](fg:#394260 bg:#212736)\
$nodejs\
$rust\
$golang\
$php\
[](fg:#212736 bg:#1d2230)\
$time\
[ ](fg:#1d2230)\
\n$character"""

[directory]
style = "fg:#e3e5e5 bg:#769ff0"
format = "[ $path ]($style)"
truncation_length = 3
truncation_symbol = "…/"

[directory.substitutions]
"Documents" = "󰈙 "
"Downloads" = " "
"Music" = " "
"Pictures" = " "

[git_branch]
symbol = ""
style = "bg:#394260"
format = '[[ $symbol $branch ](fg:#769ff0 bg:#394260)]($style)'

[git_status]
style = "bg:#394260"
format = '[[($all_status$ahead_behind )](fg:#769ff0 bg:#394260)]($style)'

[time]
disabled = false
time_format = "%R" # Hour:Minute Format
style = "bg:#1d2230"
format = '[[  $time ](fg:#a0a9cb bg:#1d2230)]($style)'
```

## Backup

### Timeshift for system restore
``` console
sudo dnf install timeshift
```

#### Configuration
1. rsync
2. choose backup location
3. set backup schema
4. choose user directories

### BackInTime for personal data backups
``` console
dnf install backintime
```

### Foxclone for cloning system
``` console
dnf remove firefox
```
