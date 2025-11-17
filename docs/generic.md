## before chroot
```
pacstrap /mnt base neovim
```
```
genfstab -U /mnt > /mnt/etc/fstab
```
```
arch-chroot /mnt
```

## beta
enable multilib
```
nvim /etc/pacman.conf
```
```
pacman -Syy
```
```
pacman -S linux-zen amd-ucode mkinitcpio openssh firewalld wireless-regdb sof-firmware lib32-mesa mesa vulkan-radeon lib32-vulkan-radeon linux-firmware-atheros linux-firmware-intel linux-firmware-other linux-firmware-realtek linux-firmware-amdgpu linux-firmware-radeon gamescope gamemode pipewire lib32-pipewire pipewire-alsa pipewire-pulse ttf-roboto kitty-terminfo git wget pipewire-jack flatpak discover fuse weston umu-launcher btop lightdm  lightdm-webkit2-greeter scx-scheds kwallet dolphin-emu networkmanager xorg-server steam waydroid kodi-gles base-devel bluez-utils cutefish-calculator cutefish-core cutefish-dock cutefish-filemanager cutefish-icons 
cutefish-launcher cutefish-qt-plugins cutefish-screenlocker cutefish-screenshot cutefish-settings cutefish-statusbar cutefish-terminal cutefish-wallpapers aria2 --noconfirm
``` 

## config
```
git clone https://github.com/blackbird-package/level-21.git /tmp/
```
```
cp -fr /tmp/base/* /
```
*radeon*
```
cp -fr /tmp/radeon/* /
```
*nvidia*
```
cp -fr /tmp/nvidia/* /
```


### hostname 
```
echo 'nama_hostname' > /etc/hostname
```
### locatime 
```
ln -sf /usr/share/zoneinfo/Asia/Jakarta /etc/localtime
```
```
hwclock --systohc
```
```
timedatectl set-ntp true
```
```
timedatectl set-timezone Asia/Jakarta
```
```
timedatectl status
```
```
systemctl enable systemd-timesyncd.service
```

### locale 
```
locale-gen
```


## preps
```
rm -fr /etc/skel/.bash*
```
```
mkdir -p /home/media/Games/{playstation1,playstation2,nintendo-swicth,nintendo-wii,playstation3,xbox360,steam,epic,ubisoft}
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
```
mkdir -p /opt/switch/ 
```
```
cd /opt/switch/ 
```
[check latest ryujinx](https://git.ryujinx.app/ryubing/canary/-/releases)
```
wget https://git.ryujinx.app/api/v4/projects/68/packages/generic/Ryubing-Canary/1.3.207/ryujinx-canary-1.3.207-linux_x64.tar.gz
```
```
tar xf ryujinx-canary-1.3.207-linux_x64.tar.gz
```
```
rm ryujinx-canary-1.3.207-linux_x64.tar.gz
```
```
mv publish engine
```
```
mkdir /opt/switch/firmware
```
```
cd /opt/switch/firmware
```
```
wget https://github.com/THZoria/NX_Firmware/releases/download/20.5.0/Firmware.20.5.0.zip
```
```
unzip Firmware.20.5.0.zip
```
```
rm Firmware.20.5.0.zip
```
```
mkdir -p /opt/switch/keyprod
```
```
cd /opt/switch/keyprod
```
```
wget https://files.prodkeys.net/ProdKeys.NET-v20.5.0.zip
```

## playstation1
```
mkdir -p /opt/playstation1/engine 
```
```
cd /opt/playstation1/engine 
```
[check latest release](https://github.com/stenzek/duckstation/releases/tag/latest) 
```
wget https://github.com/stenzek/duckstation/releases/download/latest/DuckStation-x64.AppImage
```
```
chmod +x DuckStation-x64.AppImage 
```
```
mv DuckStation-x64.AppImage latest.AppImage
```
```
mkdir -p /opt/playstation1/firmware 
```
```
cd /opt/playstation1/firmware 
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
mkdir -p /opt/playstation2/engine 
```
```
cd /opt/playstation2/engine 
```
```
wget https://github.com/PCSX2/pcsx2/releases/download/v2.4.0/pcsx2-v2.4.0-linux-appimage-x64-Qt.AppImage
```
```
chmod +x pcsx2-v2.4.0-linux-appimage-x64-Qt.AppImage 
```
```
mv pcsx2-v2.4.0-linux-appimage-x64-Qt.AppImage latest.AppImage
```
```
mkdir -p /opt/playstation2/firmware 
```
```
cd /opt/playstation2/firmware 
```
```
wget https://pcsx2bios.com/wp-content/uploads/download/ps2/ps2-bios-all-bios.zip
```
```
unzip ps2-bios-all-bios.zip 
```
```
rm ps2-bios-all-bios.zip
```


## playstation3
```
mkdir -p /opt/playstation3/engine 
```
```
cd /opt/playstation3/engine 
```
```
wget https://github.com/RPCS3/rpcs3-binaries-linux/releases/download/build-e48ba283d82ec66072596b13f4d8522d0cf4961f/rpcs3-v0.0.38-18328-e48ba283_linux64.AppImage
```
```
chmod +x rpcs3-v0.0.38-18328-e48ba283_linux64.AppImage
```
```
mv rpcs3-v0.0.38-18328-e48ba283_linux64.AppImage latest.AppImage
```

## android
```
waydroid init -s GAPPS
```
```
systemctl enable waydroid-container.service
```

## multimedia
```
rm /usr/share/wayland-sessions/kodi-gbm.desktop
```
```
rm /usr/share/xsessions/kodi.desktop
```

## booting

```
mkdir -p /boot/{efi,kernel,loader}
```

```
mkdir -p /boot/efi/{boot,linux,systemd,rescue}
```

```
mv /boot/vmlinuz-linux-zen /boot/amd-ucode.img /boot/kernel/
```

```
rm /etc/mkinitcpio.conf
```

```
rm -fr /etc/mkinitcpio.conf.d/
```

```
rm /boot/initramfs-*
```

```
bootctl --path=/boot/ install
```


## service
```
systemctl enable NetworkManager
```
```
systemctl enable lightdm
```
```
systemctl enable firewalld
```
```
systemctl enable bluetooth.service
```W

## finishing
```
chmod +x /usr/xbin/*
```
```
mkinitcpio -P
```
