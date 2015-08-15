# Maintainer: Andre Bartke

pkgname=grmon-eval
pkgver=2.0.62
pkgrel=1
pkgdesc="Gaisler debug monitor for LEON processors"
arch=('i686' 'x86_64')
url="http://www.gaisler.com/index.php/products/debug-tools/grmon"
license=('custom')
options=('!strip')
source=(
	"http://gaisler.com/anonftp/grmon/${pkgname}-${pkgver}.tar.gz"
	"http://gaisler.com/anonftp/grmon/grmon-license.txt")

if test "$CARCH" == x86_64; then
	depends=("lib32-ncurses" "libftdi" "libusb-compat" "libusbx" "lib32-nspr")
else
	depends=("ncurses" "libftdi" "libusb-compat" "libusbx" "nspr")
fi

package() {
	mkdir -p $pkgdir/usr

	cp -r $srcdir/$pkgname-$pkgver/linux/{bin,share} $pkgdir/usr
	install -Dm644 $srcdir/grmon-license.txt $pkgdir/usr/share/licenses/$pkgname/LICENSE
}

md5sums=('e0cb13c48bb0528613c7473b625c5fdd'
         '50a75f690852e1f5269f3670578ad2f0')

