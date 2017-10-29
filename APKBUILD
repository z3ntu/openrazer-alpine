# Contributor:
# Maintainer:
_pkgname=openrazer
pkgname=openrazer-meta
pkgver=2.0.0
pkgrel=0
pkgdesc="OpenRazer"
url="https://openrazer.github.io"
arch="all"
license="GPL2"
depends="openrazer-kernel-modules-dkms openrazer-daemon py3-openrazer"
install=""
subpackages="openrazer-kernel-modules-dkms openrazer-daemon py3-openrazer:py3"
source="$_pkgname-$pkgver.tar.gz::https://github.com/openrazer/openrazer/archive/v$pkgver.tar.gz
	busybox-pgrep.patch::https://github.com/openrazer/openrazer/commit/302172a07b1749b369bf45b939bcadd0830b8f18.patch"
builddir="$srcdir/$_pkgname-$pkgver"
options="!check"

package() {
	mkdir -p "$pkgdir"
}

dkms() {
	cd "$builddir"
	make DESTDIR="$subpkgdir" setup_dkms udev_install
}

daemon() {
	depends="python3 py3-setproctitle py3-gobject3 gtk+3.0"
	cd "$builddir"
	make DESTDIR="$subpkgdir" daemon_install
}

py3() {
	cd "$builddir"
	make DESTDIR="$subpkgdir" python_library_install
}

sha512sums="6c90a2217fe300dacf52c5d084cd5ba40fbd8230f2bf6134a610a02307ebb4b5487ca4a2039b2db1e5771a4ff686e66739fdd1e811b77ffa34823ee7f5ba2ea0  openrazer-2.0.0.tar.gz
85211eb9bb87e4f109373088c7f83fefe74d92ff8c7ebff8333352409078a09e57d57d39fa8cb982d08650c844a75454d97498346ac6219d62646519f44946bb  busybox-pgrep.patch"
