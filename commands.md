# Software
## Update
### Packet manager
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
dnf remove packagename
```

## History
### All updated packages
``` console
rpm -qa --qf '%{INSTALLTIME} (%{INSTALLTIME:date}): %{NAME}-%{VERSION}-%{RELEASE}.%{ARCH}\n' | sort -n
``` 
