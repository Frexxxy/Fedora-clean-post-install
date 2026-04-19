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
sudo dnf install fuse
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

### KDrive

## Configuration

## Uninstall Software
dnf remove firefox
## System settings
### Berg als Hintergrund
### Nachtlicht aktivieren nach Sonnenstand
Temperatur 3800

### Hell und Dunkel nach Sonnenstand
### Super Key + T = Terminal
