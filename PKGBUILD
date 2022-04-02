# Maintainer: John Lindgren <john@jlindgren.net>

pkgname=qmpanel
pkgver=0.1
pkgrel=1
pkgdesc="A Minimal Qt-Based Desktop Panel"
arch=("x86_64")
url="https://github.com/git-fal7/$pkgname"
source=("$pkgname::git+$url.git")
sha512sums=('SKIP')
license=("LGPL2.1")
makedepends=("cmake")
depends=(
	"glib2"
	"kwindowsystem"
	"libxcb"
	"libxcomposite"
	"libxdamage"
	"libxrender"
)

build() {
	cd "$pkgname"
	mkdir -p build
	cd build
	cmake .. -DCMAKE_INSTALL_PREFIX=/usr
	make
}

package() {
	cd "$pkgname"
	cd build
	make DESTDIR="$pkgdir" install
}
