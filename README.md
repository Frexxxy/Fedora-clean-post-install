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

## Install software
### Prereqs
``` console
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```

### DNF
``` console
sudo dnf install fuse evolution 
```

### Flatpaks
``` console
sudo flatpak install flathub it.mijorus.gearlever io.github.CyberTimon.RapidRAW app.zen_browser.zen org.kde.kate
```

### RAW Thumbnails
``` console
# Clone the repo and move to the folder containing the scripts
git clone https://github.com/emuskardin/nautilus-raw-thumbnails.git
cd nautilus-raw-thumbnails

# Install dependencies on fedora
sudo dnf install exiv2 ImageMagick perl-Image-ExifTool

# Move the thumbnailer configuration to the system directory
sudo cp exiv2raw.thumbnailer /usr/share/thumbnailers/

# Move the thumbnailer script to the bin directory and make it executable
sudo cp exiv2-thumbnailer.sh /usr/local/bin/
sudo chmod +x /usr/local/bin/exiv2-thumbnaiTerminal


# Restart Nautilus to apply the changes:
nautilus -q

# Force thumbnail generation
rm -rf ~/.cache/thumbnails/*
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
starship preset tokyo-night -o ~/.config/starship.toml
```

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

### KDrive
1. Download file from https://www.infomaniak.com/en/apps/download-kdrive
2. Install, Login

### Passwordmanager
``` console
dnf install qtpass
```

### Joplin
``` console
wget -O - https://raw.githubusercontent.com/laurent22/joplin/dev/Joplin_install_and_update.sh | bash
```

## Configuration
### Evolution
1. Add Mail account
2. Add calendar account
3. Set alias "outlook"
   
### 

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
