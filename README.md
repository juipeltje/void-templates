# Void Linux template repo for building packages with xbps-src
## Summary
This is my personal repo where i keep my template files that i use to build packages that i use on Void Linux. You can use these template files if you want, but i should note that i might not keep every template up to date. updating it yourself in that case should be fairly simple though.

## Setting up your system to build packages with template files
1. Make sure to follow the instructions on how to setup `xbps-src` first on the `void-packages` Github page: https://github.com/void-linux/void-packages <br />
2. Git clone this repo (or manually download whichever template files you want, but the rest of the readme will assume you used a git clone).
```
git clone https://github.com/juipeltje/void-templates
``` 
## liquidctl

Before building and installing liquidctl, you need to build some dependencies first. liquidctl requires `python3-colorlog` and `python3-hidapi` (not to be confused with `python3-hid`, they are two different modules!) as runtime dependencies, which are both not in the Void Linux repos.  

## picom-FT-Labs
Move the `picom-ft-labs` folder into the `srcpkgs` folder:
```
mv picom-FT-Labs-template void-packages/srcpkgs/picom-ft-labs
```
3. cd into `void-packages`, then build and install the package:
```
cd void-packages
./xbps-src pkg picom-ft-labs
sudo xbps-install --repository=hostdir/binpkgs picom-ft-labs
```
Note: This fork of picom seems to still be actively developed. if you want to update to a package with newer commits, simply edit the version and/or revision number in the template file, and then rebuild the package, and install it as an update with `xbps-install`.
