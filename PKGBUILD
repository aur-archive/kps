# Maintainer: archtux <antonio dot arias99999 at gmail dot com>

pkgname=kps
pkgver=0.9.5
pkgrel=4
pkgdesc="KDE interface to process status"
arch=('i686' 'x86_64')
url="http://www.kde-apps.org/content/show.php/KPS?content=110732"
license=('GPL2')
depends=('qt4' 'kdebase-workspace')
source=(http://www.binro.org/$pkgname-$pkgver.tar.bz2)
md5sums=('5f45d0dbc79b4634bbb78975bbb3866f')

prepare() {
  cd $srcdir/$pkgname-$pkgver

  # GCC 4.7 fix
  sed -i '21i#include <unistd.h>' src/kps.cpp
  
  mkdir build
  cd build
  cmake -DQT_QMAKE_EXECUTABLE=qmake-qt4 -DCMAKE_INSTALL_PREFIX=$KDEDIR ..
}

build() {
  cd $srcdir/$pkgname-$pkgver/build
  make
}

package() {
  cd $srcdir/$pkgname-$pkgver/build  
  make DESTDIR=$pkgdir/usr install
}
