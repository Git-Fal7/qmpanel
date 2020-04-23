# Maintainer: Jerome Leclanche <jerome@leclan.ch>

pkgname=lxqt-panel
pkgver=0.14.1
pkgrel=2
pkgdesc="The LXQt desktop panel"
arch=("x86_64")
groups=("lxqt")
url="https://lxqt.org"
license=("LGPL2.1")
depends=(
	"libdbusmenu-qt5" "libxcomposite" "lxmenu-data"
	"lxqt-globalkeys" "solid" "libxcb"
)
optdepends=(
	"libpulse: Volume control plugin"
	"alsa-lib: Volume control plugin"
	"libstatgrab: CPU monitor and Network monitor plugins"
	"libsysstat: System Statistics plugin"
	"lm_sensors: Sensors plugin"
)
makedepends=(
	"lxqt-build-tools" "liblxqt" "libpulse" "libstatgrab" "libsysstat"
	"lm_sensors" "libxdamage" "alsa-lib"
)
source=(
	"https://github.com/lxqt/$pkgname/releases/download/$pkgver/$pkgname-$pkgver.tar.xz"{,.asc}
)
sha256sums=('f8be1c1446492e0c6a639ce09fb75341f5c47e4c24f7776020f2543936e87ce4'
            'SKIP')
validpgpkeys=(
	"169704C6FB490C6892C7F23C37E0AF1FDA48F373"  # Jerome Leclanche <jerome@leclan.ch>
	"7C733BA5F585AAD669E4D23A42C9C8D3AF5EA5E3"  # Alf Gaida <agaida@siduction.org>
)


build() {
	mkdir -p build
	cd build
	cmake "$srcdir/$pkgname-$pkgver" \
		-DCMAKE_INSTALL_PREFIX=/usr
	make
}

package() {
	cd build
	make DESTDIR="$pkgdir" install
	}
