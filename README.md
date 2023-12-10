# Void Linux template repo for building packages with xbps-src
## Summary
This is my personal repo where i keep my template files that i use to build packages that i use on Void Linux. You can use these template files if you want, but i should note that i might not keep every template up to date. updating it yourself in that case should be fairly simple though.

the following package templates are in my repo:

- [liquidctl](#liquidctl)
- python3-colorlog (used as a dependency for liquidctl)
- python3-hidapi (used as a dependency for liquidctl)
- [fastfetch](#fastfetch)
- [mint-y-icons](#mint-y-icons)
- [phinger-cursors](#phinger-cursors)
- [tokyo-night-gtk](#tokyo-night-gtk)
- [nordic-gtk](#nordic-gtk)
- [nordic-kvantum](#nordic-kvantum)
- [gruvbox-material-gtk](#gruvbox-material-gtk)
- [gruvbox-kvantum](#gruvbox-kvantum)
- [ubuntu-nerd-font-ttf](#ubuntu-nerd-font-ttf)
- [mononoki-nerd-font-ttf](#mononoki-nerd-font-ttf)
- [picom-FT-Labs](#picom-ft-labs)

## Setting up your system to build packages with template files
1. make sure to follow the instructions on how to setup `xbps-src` first on the `void-packages` Github page: https://github.com/void-linux/void-packages <br />
2. git clone this repo (or manually download whichever template files you want, but the rest of the readme will assume you used a git clone).
```
git clone https://github.com/juipeltje/void-templates
``` 
## liquidctl

Before building and installing liquidctl, you need to build some dependencies first. liquidctl requires `python3-colorlog` and `python3-hidapi` (not to be confused with `python3-hid`, they are two different modules!) as runtime dependencies, which are both not in the Void Linux repos.
1. copy the required folders into the `void-packages/srcpkgs` folder:
```
cp -r void-templates/srcpkgs/python3-colorlog void-packages/srcpkgs/
cp -r void-templates/srcpkgs/python3-hidapi void-packages/srcpkgs/
cp -r void-templates/srcpkgs/liquidctl void-packages/srcpkgs/
```
2. now cd into `void-packages` and build the `python3-colorlog` and `python3-hidapi` packages using `xbps-src`:
```
cd void-packages
./xbps-src pkg python3-colorlog
./xbps-src pkg python3-hidapi
```
3. now finally build and install the `liquidctl` package:
```
./xbps-src pkg liquidctl
sudo xbps-install -R hostdir/binpkgs liquidctl
```

## fastfetch

1. copy the `fastfetch` folder into the `void-packages/srcpkgs` folder:
```
cp -r void-templates/srcpkgs/fastfetch void-packages/srcpkgs/
```
2. cd into `void-packages`, then build and install the package:
```
./xbps-src pkg fastfetch
sudo xbps-install -R hostdir/binpkgs fastfetch
```

## mint-y-icons

1. copy the `mint-y-icons` folder into the `void-packages/srcpkgs` folder:
```
cp -r void-templates/srcpkgs/mint-y-icons void-packages/srcpkgs/
```
2. cd into `void-packages`, then build and install the package:
```
./xbps-src pkg mint-y-icons
sudo xbps-install -R hostdir/binpkgs mint-y-icons
```

## phinger-cursors

1. copy the `phinger-cursors` folder into the `void-packages/srcpkgs` folder:
```
cp -r void-templates/srcpkgs/phinger-cursors void-packages/srcpkgs/
```
2. cd into `void-packages`, then build and install the package:
```
./xbps-src pkg phinger-cursors
sudo xbps-install -R hostdir/binpkgs phinger-cursors
```

## tokyo-night-gtk

1. copy the `tokyo-night-gtk` folder into the `void-packages/srcpkgs` folder:
```
cp -r void-templates/srcpkgs/tokyo-night-gtk void-packages/srcpkgs/
```
2. cd into `void-packages`, then build and install the package:
```
./xbps-src pkg tokyo-night-gtk
sudo xbps-install -R hostdir/binpkgs tokyo-night-gtk
```

## nordic-gtk

1. copy the `nordic-gtk` folder into the `void-packages/srcpkgs` folder:
```
cp -r void-templates/srcpkgs/nordic-gtk void-packages/srcpkgs/
```
2. cd into `void-packages`, then build and install the package:
```
./xbps-src pkg nordic-gtk
sudo xbps-install -R hostdir/binpkgs nordic-gtk
```

## nordic-kvantum

1. copy the `nordic-kvantum` folder into the `void-packages/srcpkgs` folder:
```
cp -r void-templates/srcpkgs/nordic-kvantum void-packages/srcpkgs/
```
2. cd into `void-packages`, then build and install the package:
```
./xbps-src pkg nordic-kvantum
sudo xbps-install -R hostdir/binpkgs nordic-kvantum
```

## gruvbox-material-gtk

1. copy the `gruvbox-material-gtk` folder into the `void-packages/srcpkgs` folder:
```
cp -r void-templates/srcpkgs/gruvbox-material-gtk void-packages/srcpkgs/
```
2. cd into `void-packages`, then build and install the package:
```
./xbps-src pkg gruvbox-material-gtk
sudo xbps-install -R hostdir/binpkgs gruvbox-material-gtk
```

## gruvbox-kvantum

1. copy the `gruvbox-kvantum` folder into the `void-packages/srcpkgs` folder:
```
cp -r void-templates/srcpkgs/gruvbox-kvantum void-packages/srcpkgs/
```
2. cd into `void-packages`, then build and install the package:
```
./xbps-src pkg gruvbox-kvantum
sudo xbps-install -R hostdir/binpkgs gruvbox-kvantum
```

## ubuntu-nerd-font-ttf

1. copy the `ubuntu-nerd-font-ttf` folder into the `void-packages/srcpkgs` folder:
```
cp -r void-templates/srcpkgs/ubuntu-nerd-font-ttf void-packages/srcpkgs/
```
2. cd into `void-packages`, then build and install the package:
```
./xbps-src pkg ubuntu-nerd-font-ttf
sudo xbps-install -R hostdir/binpkgs ubuntu-nerd-font-ttf
```

## mononoki-nerd-font-ttf

1. copy the `mononoki-nerd-font-ttf` folder into the `void-packages/srcpkgs` folder:
```
cp -r void-templates/srcpkgs/mononoki-nerd-font-ttf void-packages/srcpkgs/
```
2. cd into `void-packages`, then build and install the package:
```
./xbps-src pkg mononoki-nerd-font-ttf
sudo xbps-install -R hostdir/binpkgs mononoki-nerd-font-ttf
```

## picom-FT-Labs
1. copy the `picom-ft-labs` folder into the `void-packages/srcpkgs` folder:
```
cp -r void-templates/srcpkgs/picom-ft-labs void-packages/srcpkgs/
```
2. cd into `void-packages`, then build and install the package:
```
cd void-packages
./xbps-src pkg picom-ft-labs
sudo xbps-install -R hostdir/binpkgs picom-ft-labs
```
