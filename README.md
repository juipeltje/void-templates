# Void Linux template file for xbps-src
How to install:
1. make sure to follow the instructions on how to setup xbps-src first on the void-packages Github page: https://github.com/void-linux/void-packages
Note: don't forget to also enable the ALLOW_RESTRICTED option mentioned in their instructions.
2. git clone this repo and move the picom-ft-labs folder into the srcpkgs folder:
```
git clone https://github.com/juipeltje/picom-FT-Labs-template
mv picom-FT-LABS-template void-packages/srcpkgs/picom-ft-labs
```
3. cd into voi-packages, then build and install the package:
```
cd void-packages
./xbps-src pkg picom-ft-labs
sudo xbps-install --repository=hostdir/binpkgs picom-ft-labs
```
This fork of picom seems to still be actively developed. if you want to update to a package with newer commits, simply edit the version and/or revision number in the template file, and then rebuild the package, and install it as an update with xbps-install.
