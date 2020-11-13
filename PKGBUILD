pkgname=wbg
pkgver=1.0.0
pkgrel=1
pkgdesc="Super simple wallpaper application"
arch=('x86_64' 'aarch64')
url=https://codeberg.org/dnkl/wbg
license=(mit)
makedepends=('meson' 'ninja' 'tllist>=1.0.1')
depends=('wayland' 'libjpeg-turbo' 'libpng')
source=()

pkgver() {
  cd ../.git &> /dev/null && git describe --tags --long | sed 's/^v//;s/\([^-]*-g\)/r\1/;s/-/./g' ||
      head -3 ../meson.build | grep version | cut -d "'" -f 2
}

build() {
  meson --prefix=/usr --buildtype=release --wrap-mode=nofallback ..
  ninja
}

package() {
  DESTDIR="${pkgdir}/" ninja install
}
