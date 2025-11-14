## alpha
```
pacman -S linux-zen amd-ucode mkinitcpio cutefish-calculator cutefish-core cutefish-dock cutefish-filemanager cutefish-icons cutefish-launcher cutefish-qt-plugins cutefish-screenlocker cutefish-screenshot cutefish-settings cutefish-statusbar cutefish-terminal cutefish-wallpapers openssh firewalld systemd-ukify wireless-regdb sof-firmware lib32-mesa mesa  vulkan-radeon lib32-vulkan-radeon linux-firmware-atheros linux-firmware-intel linux-firmware-realtek linux-firmware-amdgpu linux-firmware-radeon gamescope gamemode pipewire pipewire-pulse sddm ttf-roboto kitty-terminfo git wget pipewire-jack flatpak cosmic-store flatpak-kcm fuse weston umu-launcher
```

## beta
```
pacman -S linux-zen amd-ucode mkinitcpio openssh firewalld systemd-ukify wireless-regdb sof-firmware lib32-mesa mesa  vulkan-radeon lib32-vulkan-radeon linux-firmware-atheros linux-firmware-intel linux-firmware-realtek linux-firmware-amdgpu linux-firmware-radeon gamescope gamemode pipewire pipewire-pulse sddm ttf-roboto kitty-terminfo git wget pipewire-jack flatpak cosmic-store flatpak-kcm fuse weston umu-launcher
```

## steam
```
pacman -S steam
```

## heroic
```
git clone https://aur.archlinux.org/http-parser.git 
```
```
cd http-parser
```
```
makepkg -rsi
```
```
wget https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher/releases/download/v2.18.1/Heroic-2.18.1-linux-x64.pacman
```
```
pacman -U Heroic-2.18.1-linux-x64.pacman
```
## nintendo switch
[check latest ryujinx](https://git.ryujinx.app/ryubing/canary/-/releases)
```
wget https://git.ryujinx.app/api/v4/projects/68/packages/generic/Ryubing-Canary/1.3.207/ryujinx-canary-1.3.207-linux_x64.tar.gz
```
## nintendo wii/gamecube
```
flatpak remote-add --if-not-exists dolphin https://flatpak.dolphin-emu.org/releases.flatpakrepo
```
```
flatpak install dolphin org.DolphinEmu.dolphin-emu 
```
## playstation2
```
flatpak install flathub net.pcsx2.PCSX2 
```
## playstation1
```
cd /opt 
```
```
mkdir Duckers
```
```
cd Duckers
```
[check latest release](https://github.com/stenzek/duckstation/releases/tag/latest) 
```
 wget https://github.com/stenzek/duckstation/releases/download/latest/DuckStation-x64-SSE2.AppImage
```
```
chmod +x DuckStation-x64-SSE2.AppImage 
```

## android
```
pacman -S waydroid
```
```
waydroid init -s GAPPS
```
```
systemctl enable waydroid-container.service
```
