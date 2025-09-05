pkgname=libxres
pkgver=1.2.2
pkgrel=1
pkgdesc="X11 Resource extension library"
arch=('x86_64')
url="https://xorg.freedesktop.org"
license=('X11')
depends=(
    'glibc'
    'libx11'
    'libxext'
    'xorgproto'
)
makedepends=('xorg-util-macros')
source=(https://www.x.org/pub/individual/lib/libXres-${pkgver}.tar.xz)
sha256sums=(9a7446f3484b9b7538ac5ee30d2c1ce9e5b7fbbaf1440e02f6cca186a1fa745f)

build() {
    cd libXres-${pkgver}

    local configure_args=(
        --sysconfdir=/etc
        --localstatedir=/var
        --disable-static
        --docdir=/usr/share/doc/libXres-${pkgver}
        ${configure_options}
    )

    ./configure "${configure_args[@]}"

    make
}

package() {
    cd libXres-${pkgver}

    make DESTDIR=${pkgdir} install
}

