# Requirement: HeeksCAD #
HeeksCNC requires HeeksCAD, please follox instructions available at:
https://code.google.com/p/heekscad/wiki/BuildDebianPackages

## Fetch sources ##
```
svn checkout http://heekscnc.googlecode.com/svn/trunk/ heekscnc
cd heekscnc
```

## Build packages ##

```
dpkg-buildpackage -b -us -uc
cd ..
```

This will produces 1 package: heekscnc.

## Install runtime dependencies ##
### python-area ###
Be sure that python-area package from libarea is correctly installed.

### python-ocl ###
Then you have to build and install Debian packages of OpenCAMlib.
```
git clone https://github.com/aewallin/opencamlib.git
cd opencamlib
bzr branch lp:~neomilium/opencamlib/packaging debian
dpkg-buildpackage -b -us -uc
cd ..
sudo dpkg -i python-ocl*.deb
```

## Install packages ##
```
sudo dpkg -i heekscnc*.deb
```

## Enjoy! ##
```
heekscad
```