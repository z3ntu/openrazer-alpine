# Contributor:
# Maintainer:
pkgname=openrazer
pkgver=2.0.0
pkgrel=0
pkgdesc="OpenRazer"
url="https://openrazer.github.io"
arch="all"
license="GPL2"
depends="python3 py3-setproctitle py3-gobject3 gtk+3.0"
makedepends=""
install=""
#subpackages="$pkgname-doc"
source="${pkgname}-${pkgver}.tar.gz::https://github.com/openrazer/openrazer/archive/v${pkgver}.tar.gz"
builddir="$srcdir/$pkgname-$pkgver"
options="!check"

build() {
	cd "$builddir"
}

package() {
	cd "$builddir"
	make DESTDIR=$pkgdir python_library_install
	make DESTDIR=$pkgdir daemon_install
	make DESTDIR=$pkgdir setup_dkms udev_install
}

sha512sums="6c90a2217fe300dacf52c5d084cd5ba40fbd8230f2bf6134a610a02307ebb4b5487ca4a2039b2db1e5771a4ff686e66739fdd1e811b77ffa34823ee7f5ba2ea0  openrazer-2.0.0.tar.gz"
