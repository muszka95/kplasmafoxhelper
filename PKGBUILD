pkgname=kplasmafoxhelper
pkgver=5.0.5
pkgrel=6
#epoch=1
pkgdesc="Plasmafox KDE Integration (kmozillahelper from openSUSE)."
url="https://github.com/openSUSE/kmozillahelper"
arch=("i686" "x86_64")
license=('MIT')
depends=("kio" "knotifications" "kwindowsystem" "ki18n")
makedepends=("cmake" "extra-cmake-modules" "git")
source=(git+https://github.com/torvic9/kplasmafoxhelper.git)
md5sums=('SKIP')

build() {
	mkdir -p build
	cd build
	cmake -DCMAKE_INSTALL_PREFIX=/usr -DBUILD_TESTING=OFF -DCMAKE_BUILD_TYPE=Release ../${pkgname}
	make
}

package() {
	make -C build DESTDIR="$pkgdir" install
	install -Dm644 "$pkgname/LICENSE" "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

