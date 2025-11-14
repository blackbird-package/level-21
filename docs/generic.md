## before chroot
```
pacstrap /mnt base base-devel
```
```
genfstab -U /mnt > /mnt/etc/fstab
```
```
arch-chroot /mnt
```

## alpha
```
pacman -S linux-zen amd-ucode mkinitcpio cutefish-calculator cutefish-core cutefish-dock cutefish-filemanager cutefish-icons cutefish-launcher cutefish-qt-plugins cutefish-screenlocker cutefish-screenshot cutefish-settings cutefish-statusbar cutefish-terminal cutefish-wallpapers openssh firewalld systemd-ukify wireless-regdb sof-firmware lib32-mesa mesa  vulkan-radeon lib32-vulkan-radeon linux-firmware-atheros linux-firmware-intel linux-firmware-realtek linux-firmware-amdgpu linux-firmware-radeon gamescope gamemode pipewire pipewire-pulse ttf-roboto kitty-terminfo git wget pipewire-jack flatpak cosmic-store flatpak-kcm fuse weston umu-launcher sddm
```

## beta
```
pacman -S linux-zen amd-ucode mkinitcpio openssh firewalld systemd-ukify wireless-regdb sof-firmware lib32-mesa mesa  vulkan-radeon lib32-vulkan-radeon linux-firmware-atheros linux-firmware-intel linux-firmware-realtek linux-firmware-amdgpu linux-firmware-radeon gamescope gamemode pipewire pipewire-pulse  ttf-roboto kitty-terminfo git wget pipewire-jack flatpak cosmic-store flatpak-kcm fuse weston umu-launcher gdm
```
## steam
```
pacman -S steam
```
## user
```
useradd -m [name]
```
```
passwd [name]
```
```
usermod -aG wheel [name]
```
*jangan lupa untuk uncomment group wheel pada /etc/sudoers*


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
pacman -S dolphin-emu
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
chmod +x DuckStation-x64.AppImage 
```
```
su [nama user]
```
```
mkdir -p $HOME/.local/bios/playstation1
```
```
cd $HOME/.local/bios/playstation1
```
```
wget https://psbios.me/download/ps1/SCPH1001.BIN
```
```
wget https://psbios.me/download/ps1/SCPH5500.BIN
```
```
wget https://psbios.me/download/ps1/SCPH-7502.BIN
```
## playstation2
```
mkdir -p /opt/Pcsx2
```
```
cd /opt/Pcsx2 
```
```
wget https://github.com/PCSX2/pcsx2/releases/download/v2.4.0/pcsx2-v2.4.0-linux-appimage-x64-Qt.AppImage
```
```
chmod +x pcsx2-v2.4.0-linux-appimage-x64-Qt.AppImage 
```
## playstation2
```
mkdir -p /opt/Rpcs3
```
```
cd /opt/Rpcs3 
```
```
wget https://github.com/RPCS3/rpcs3-binaries-linux/releases/download/build-e48ba283d82ec66072596b13f4d8522d0cf4961f/rpcs3-v0.0.38-18328-e48ba283_linux64.AppImage
```
```
chmod +x rpcs3-v0.0.38-18328-e48ba283_linux64.AppImage
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


## configuration
```
git clone https://github.com/blackbird-package/level-21 /tmp
```
```
cp -fr /tmp/level-21/* /
```
