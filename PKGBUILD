
pkgname="plasma-wallpaper-dreamdesktop"
pkgver="0.3.0"
pkgrel=1
pkgdesc="Innovative animated desktop wallpaper for KDE"
arch=(x86_64)
url="http://www.jarzebski.pl/projekty/dreamdesktop.html"
license=('GPL')
depends=('kdelibs' 'ffmpeg')
makedepends=('automoc4' 'cmake')
source=("http://www.jarzebski.pl/files/dreamdesktop/$pkgname-$pkgver.tar.bz2")
md5sums=('da6213df1c214eabf0640ec11fdfb398')

build() {
  cd "$srcdir/$pkgname"
  mkdir -p build

  cd build/
  cmake .. \
	-DCMAKE_INSTALL_PREFIX=`kde4-config --prefix=/usr`
  make
}

package() {
  cd "$srcdir/$pkgname/build"

  make DESTDIR="$pkgdir/" install
}
