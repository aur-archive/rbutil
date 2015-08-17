 
pkgname=rbutil
_pkgname=RockboxUtility
pkgver=1.3.1
pkgrel=1
pkgdesc="Rockbox Utility: this is the automated installer tool for Rockbox"
arch=('i686' 'x86_64')
url="http://www.rockbox.org/twiki/bin/view/Main/RockboxUtility"
license=("GPL")
depends=('qt>=4.3.0' 'libusb')
provides=('rbutilqt' 'rbutil')
conflicts=('rbutil-bin' 'rbutil-svn')
source=(http://download.rockbox.org/${pkgname}/source/$_pkgname-v${pkgver}-src.tar.bz2 $pkgname.desktop)
md5sums=('4805041c58536a1a85c95234faefc3d4'
         'c10d3c5bac897097f63770578ae322c2')

build() {
	cd $srcdir/${_pkgname}-v${pkgver}/$pkgname/rbutilqt
	lrelease rbutilqt.pro
	qmake
	make	
} 

package(){
	install -D -m644 $srcdir/${_pkgname}-v${pkgver}/$pkgname/rbutilqt/icons/rockbox-64.png $pkgdir/usr/share/pixmaps/$pkgname.png
	install -D -m644 $srcdir/$pkgname.desktop $pkgdir/usr/share/applications/$pkgname.desktop
	install -D -m755 $srcdir/${_pkgname}-v${pkgver}/$pkgname/rbutilqt/RockboxUtility $pkgdir/usr/bin/$pkgname
}
