# Maintainer:
# Contributor: Roman Kyrylych <Roman.Kyrylych@gmail.com>

pkgname=libgtksourceviewmm
pkgver=0.3.1
pkgrel=2
pkgdesc="A C++ API for gtksourceview"
arch=('i686' 'x86_64')
url="http://projects.gnome.org/gtksourceviewmm/"
license=('LGPL')
depends=('gtkmm' 'gtksourceview')
makedepends=('doxygen')
replaces=('gtksourceviewmm')
options=('!libtool' '!emptydirs')
source=(ftp://ftp.gnome.org/pub/gnome/sources/$pkgname/0.3/$pkgname-$pkgver.tar.bz2
	'gcc4.4.patch')
md5sums=('44282a68f4bbd5fc20c49d3c486d11f2'
         '98510998df9bc6944004819ef3654de4')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  patch -Np1 -i ${srcdir}/gcc4.4.patch
  
  ./configure --prefix=/usr
  make || return 1
  make DESTDIR=${pkgdir} install
}
