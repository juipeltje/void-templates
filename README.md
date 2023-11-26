# Void Linux template repo for building packages with xbps-src
## Summary
This is my personal repo where i keep my template files that i use to build packages that i use on Void Linux. You can use these template files if you want, but i should note that i might not keep every template up to date. updating it yourself in that case should be fairly simple though.

the following package templates are in my repo:

- [liquidctl](liquidctl)
- python3-colorlog (used as a dependency for liquidctl)
- python3-hidapi (used as a dependency for liquidctl)
- [picom-FT-Labs](picom-ft-labs)

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
2. now build the `python3-colorlog` and `python3-hidapi` packages using `xbps-src`:
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

## picom-FT-Labs
copy the `picom-ft-labs` folder into the `srcpkgs` folder:
```
cp -r picom-FT-Labs-template void-packages/srcpkgs/picom-ft-labs
```
3. cd into `void-packages`, then build and install the package:
```
cd void-packages
./xbps-src pkg picom-ft-labs
sudo xbps-install --repository=hostdir/binpkgs picom-ft-labs
```
Note: This fork of picom seems to still be actively developed. if you want to update to a package with newer commits, simply edit the version and/or revision number in the template file, and then rebuild the package, and install it as an update with `xbps-install`.
