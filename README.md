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
### Berg als Hintergrund

### Nachtlicht aktivieren nach Sonnenstand
Temperatur 3800

### Hell und Dunkel nach Sonnenstand

### Super Key + T = Terminal

## Install software
### Prereqs
``` console
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```

### DNF
``` console
sudo dnf install fuse evolution 
```

#### Configuration Evolution
1. Add Mail account
2. Add calendar account
3. Set alias "outlook"


### Flatpaks
``` console
sudo flatpak install flathub it.mijorus.gearlever io.github.CyberTimon.RapidRAW app.zen_browser.zen org.kde.kate md.obsidian.Obsidian
```

### KDrive
1. Download file from https://www.infomaniak.com/en/apps/download-kdrive
2. Install, Login

### Passwordmanager

### Backup

#### Timeshift for system restore
``` console
sudo dnf install timeshift
```

##### Configuration
1. rsync
2. choose backup location
3. set backup schema
4. choose user directories
5. 

#### BackInTime for personal data backups
``` console
dnf remove firefox
```

#### Foxclone for cloning system
``` console
dnf remove firefox
```

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
