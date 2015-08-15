# Maintainer: Lukas Jirkovsky <l.jirkovsky@gmail.com>
pkgname=gemrb
pkgver=0.7.2
pkgrel=1
pkgdesc="OSS implementation of Bioware's Infinity Engine which supports eg. Baldur's Gate"
arch=('i686' 'x86_64')
url="http://www.gemrb.org/"
license=('GPL')
depends=('python2' 'openal' 'libpng' 'sdl_mixer')
# optionally it is possible to build vlc plugin too
makedepends=('cmake')
install=gemrb.install
options=('!libtool')
source=("http://downloads.sourceforge.net/sourceforge/gemrb/$pkgname-$pkgver.tar.gz")
md5sums=('4260fcd42f42ce9232668b202b320b29')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  if [ ! -d "$srcdir/build" ] ; then
    mkdir "$srcdir/build"
  fi
  cd "$srcdir/build"

  cmake -DCMAKE_INSTALL_PREFIX=/usr ../$pkgname-$pkgver
  make
}

package() {
  cd "$srcdir"/build
  make DESTDIR="$pkgdir" install
}

