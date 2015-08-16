# Contributor : Geraud Le Falher <daureg@gmail.com>

pkgname=log4cpp
pkgver=1.0
pkgrel=5
pkgdesc="A library of C++ classes for flexible logging to files, syslog, IDSA and other destinations."
url="http://log4cpp.hora-obscura.de/"
license=('LGPL')
arch=('i686' 'x86_64')
source=(http://downloads.sourceforge.net/$pkgname/$pkgname-$pkgver.tar.gz gcc43.patch)
md5sums=('1face50ead0790d1297dfb04bacf273c'
         '09a6fd8ab6527a417c97c4db5215e558')
depends=('gcc-libs')
makedepends=( 'patch' 'make' 'gcc' )
options=('!libtool')

build() {
	cd $startdir/src/$pkgname-$pkgver
  patch -Np1 -i $srcdir/gcc43.patch
  ./configure --prefix=/usr --disable-doxygen --disable-dot --without-idsa || return 1
	make || return 1
	make DESTDIR=${startdir}/pkg install || return 1
}
# vim: set ft=sh ts=2 sw=2 et:
