pkgname=valijson-git
pkgver=a64c3c4
pkgrel=1
pkgdesc="Header-only C++ library for JSON Schema validation"

arch=('any')
url="https://github.com/tristanpenman/valijson"
license=('BSD')
conflicts=('valijson')
provides=('valijson')
makedepends=('git')
source=('git+https://github.com/tristanpenman/valijson.git')
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/valijson"
  # Migrate to `git describe` on first tagged release
  git rev-parse --short HEAD
}

build() {
  true # header-only library
}

package() {
  mkdir -p "$pkgdir/usr/include"
  cp -r "$srcdir/valijson/include/valijson" "$pkgdir/usr/include"
  find "$pkgdir/usr/include/valijson/" -type d -exec chmod 755 {} \;
  find "$pkgdir/usr/include/valijson/" -type f -exec chmod 644 {} \;
}
