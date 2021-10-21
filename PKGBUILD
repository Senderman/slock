# Maintainer: Fyodor Doletov <doletov.fyodor@yandex.ru>
# Contributor: Sergej Pupykin <pupykin.s+arch@gmail.com>
# Contributor: Sebastian A. Liem <sebastian at liem dot se>

pkgname=slock-senderman-edition-git
_pkgname=slock
pkgver=1.4
pkgrel=5
pkgdesc="A simple screen locker for X"
arch=('x86_64')
url="https://github.com/Senderman/slock"
license=('MIT')
depends=('libxext' 'libxrandr')
provides=('slock')
conflicts=('slock')
source=("$_pkgname::git+$url.git")
sha256sums=('SKIP')

prepare() {
  cd "$_pkgname"
}

build() {
  cd "$_pkgname"
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
  cd "$_pkgname"
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -m644 -D LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
