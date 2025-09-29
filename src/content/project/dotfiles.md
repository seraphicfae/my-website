---
title: 'Dotfiles'
description: 'No place like ~'
pubDate: 'May 23 2025'
heroImage: '/assets/dotfiles-hero.png'
---

please check <u>[Github](https://github.com/seraphicfae/hyprland-dotfiles)</u> for the latest update

Thanks to:
- <u>[LinuxMobile](https://github.com/linuxmobile)</u> for the base config
- <u>[Catppuccin](https://github.com/catppuccin)</u> for the amazing themes
- <u>[Adi1090x](https://github.com/adi1090x/rofi/)</u> for the incredible Rofi setup

## Showcase
<video controls width="100%" style="max-width: 1080px;">
  <source src="/assets/showcase.mp4" type="video/mp4">
  Your browser doesn’t support HTML5 video.
</video>

---

<br>

## Quick Install:
> **Don't run random scripts blindly.**

```bash
git clone https://github.com/seraphicfae/hyprland-dotfiles
cd hyprland-dotfiles
./setup.sh
```

---

<br>

## Manual Install: (Advanced users)

<br>

### Dependencies

```bash
paru -S --needed --noconfirm \
blueman bluez bluez-utils cava fastfetch ffmpegthumbnailer grim gvfs gvfs-mtp \
hyprland hyprlock hyprpicker kitty kvantum mako matugen-bin mission-center \
mpv mtpfs nautilus network-manager-applet networkmanager noto-fonts-cjk \
noto-fonts-emoji noto-fonts-extra nwg-look obs-studio papirus-icon-theme \
pavucontrol qt5-wayland qt6-wayland qt6ct rofi sddm sddm-theme-catppuccin \
slurp starship swww ttf-jetbrains-mono-nerd viewnior waybar wl-clipboard \
xdg-desktop-portal xdg-desktop-portal-gtk xdg-desktop-portal-hyprland \
xdg-user-dirs xorg-xwayland zed zsh && rm -rf $HOME/paru
```
<br>


#### Steps
```bash
cd hyprland-dotfiles

mkdir -p "$HOME/.config"
cp -r .config/* "$HOME/.config/"

mkdir -p "$HOME/.local/bin"
mkdir -p "$HOME/.local/share"

cp -r .local/bin/* "$HOME/.local/bin/"

cp -r .local/share/icons "$HOME/.local/share/"
cp -r .local/share/themes "$HOME/.local/share/"
```

<br>

### QoL/Extra (Recommended, but not need)
```bash
cp -r $HOME/.config/wallpapers/wallpaper_01.png $HOME/.cache/current_wallpaper
xdg-mime default org.gnome.Nautilus.desktop inode/directory
```

<br>

#### Finalizing
```bash
sudo systemctl enable NetworkManager
sudo systemctl enable bluetooth
sudo systemctl enable sddm

echo -e "[Theme]\nCurrent=catppuccin-mocha" | sudo tee /etc/sddm.conf

git clone --depth=1 https://github.com/mattmc3/antidote.git "$HOME/.config/zsh/antidote"

chsh -s /usr/bin/zsh

export ZDOTDIR="$HOME/.config/zsh"

reboot
```

---
<br>

## FAQ / Common Issues
**My temperature module doesn’t appear in the waybar?** \
Look in waybar and set it to your correct thermal zone.

**MPRIS module is empty** \
It only shows when media is playing.

**My icons look weird/dont show** \
With your package manager, download JetBrainsMono Nerd Font.
