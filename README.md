# Void Linux template repo for building packages with xbps-src
## Summary
This is my personal repo where i keep my template files that i use to build packages that i use on Void Linux. You can use these template files to build these packages yourself if you want. some of these templates are unmaintained because i am not using them anymore. these templates will be marked as "(unmaintained)" in the list down below.

the following package templates are in my repo:

- liquidctl
- python3-hidapi (used as a dependency for liquidctl)
- mint-y-icons
- phinger-cursors
- tokyo-night-gtk
- nordic-gtk
- gruvbox-material-gtk
- ubuntu-nerd-font-ttf
- mononoki-nerd-font-ttf
- regreet
- ueberzugpp (unmaintained)
- vita3k (unmaintained)
- nordic-kvantum (unmaintained)
- gruvbox-kvantum (unmaintained)
- picom-FT-Labs (unmaintained)

## Setting up your system to build packages with template files
1. make sure to follow the instructions on how to setup `xbps-src` first on the `void-packages` Github page: https://github.com/void-linux/void-packages <br />
2. git clone this repo (or manually download whichever template files you want, but the rest of the readme will assume you used a git clone).
```
git clone https://github.com/juipeltje/void-templates
``` 
## Building and installing a package
for most of these templates, building them and installing the package is the exact same simple process, so down below is an instruction on how to do it. replace `package-name` with whatever template it is that you're trying to build.  

1. copy the template folder into the `void-packages/srcpkgs` folder:
```
cp -r void-templates/srcpkgs/package-name void-packages/srcpkgs/
```
2. cd into `void-packages`, then build and install the package:
```
./xbps-src pkg package-name
sudo xbps-install -R hostdir/binpkgs package-name
```

## liquidctl

Before building and installing liquidctl, you need to build a dependency first. liquidctl requires `python3-hidapi` (not to be confused with `python3-hid`, they are two different modules!) as a runtime dependency, which is not in the Void Linux repos.
1. copy the required folders into the `void-packages/srcpkgs` folder:
```
cp -r void-templates/srcpkgs/python3-hidapi void-packages/srcpkgs/
cp -r void-templates/srcpkgs/liquidctl void-packages/srcpkgs/
```
2. now cd into `void-packages` and build the `python3-hidapi` package using `xbps-src`:
```
cd void-packages
./xbps-src pkg python3-hidapi
```
3. now finally build and install the `liquidctl` package:
```
./xbps-src pkg liquidctl
sudo xbps-install -R hostdir/binpkgs liquidctl
```
