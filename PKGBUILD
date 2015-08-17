# Author: Ole Jon Bjørkum <olejon88 at gmail dot com>
# Maintainer: OldShatterhand <OldShatterhand at gmx-topmail dot de>
pkgname=spotcommander-xampp
_pkgname=spotcommander
pkgver=6.0
pkgrel=1
pkgdesc="An Web-based remote control for the official Spotify client for GNU/Linux"
url="https://code.google.com/p/spotcommander/"
_url="http://www.olejon.net"
license=('GPLv3')
arch=('any')
install=${_pkgname}.install
depends=('xampp' 'xautomation' 'inotify-tools' 'wmctrl')
source=("${_url}/code/${_pkgname}/files/${_pkgname}-${pkgver}.tar.bz2"
	configpatch.patch
	#${_pkgname}.install
)
md5sums=('3d645767d40f5c8dfe222ad3de17ef08'
	 'a2d9216791927e936ed78b0095332c1b'
#	 'a5b75fc1179f1169f210827b4d0421bf'
)

build() {
cd $srcdir/${_pkgname}
patch -Np0 < $srcdir/configpatch.patch
mkdir $pkgdir/opt/
mkdir $pkgdir/opt/lampp/
mkdir $pkgdir/opt/lampp/htdocs/
mv $srcdir/${_pkgname} $pkgdir/opt/lampp/htdocs/${_pkgname}
cd $pkgdir/opt/lampp/htdocs/${_pkgname}
chmod 755 .
chmod 755 ./bin/*
chmod 666 ./sh/*.txt
chmod 755 ./sh/*.sh
chmod 777 ./lib/cache
chmod -R 777 ./db/

}
