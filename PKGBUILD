pkgname=spotlight
pkgver=0.0.1
pkgrel=3
pkgdesc="Spotlight for Linux: OSX style app finder."
arch=('aarch64')
url="https://github.com/elementary-dev/spotlight"
license=('GPL3')
depends=('libgee>=0.18.0' 'gnome-menus>=3.13.0' 'libwnck3>=3.20.0' 'glib2>=2.50.0' 'glibc>=2.28.0' 'gtk3>=3.22.0' 'cairo>=1.15.0' 'gdk-pixbuf2>=2.36.0')
makedepends=('meson' 'ninja' 'vala>=0.28.0')
source=("https://github.com/elementary-dev/spotlight/archive/v$pkgver.tar.gz")
sha256sums=("SKIP")

prepare() {
  rm -rf build
}

build() {
  cd "$srcdir/$pkgname-$pkgver"
  meson . build --prefix /usr
  ninja -C build
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  DESTDIR="$pkgdir" ninja -C build install
}

