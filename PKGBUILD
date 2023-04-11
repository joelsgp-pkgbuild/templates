# Maintainer: jmcb <joelsgp@protonmail.com>
# https://wiki.archlinux.org/title/Arch_package_guidelines
pkgname=NAME
pkgver=VERSION
pkgrel=1
pkgdesc=""
arch=('x86_64')
url=""
license=('GPL3')
depends=()
makedepends=()
checkdepends=()
optdepends=()
provides=()
conflicts=()
source=("$pkgname-$pkgver.tar.gz"
        "$pkgname-$pkgver.patch")
sha256sums=()

prepare() {
  cd "$pkgname-$pkgver"
  patch -p1 -i "$srcdir/$pkgname-$pkgver.patch"
}

build() {
  cd "$pkgname-$pkgver"
  ./configure --prefix=/usr
  make
}

check() {
  cd "$pkgname-$pkgver"
  make -k check
}

package() {
  cd "$pkgname-$pkgver"
  make DESTDIR="$pkgdir/" install
}
