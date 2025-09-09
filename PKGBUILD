pkgname=libxres
pkgver=1.2.3
pkgrel=2
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
sha256sums=(d2de8f5401d6c86a8992791654547eb8def585dfdc0c08cc16e24ef6aeeb69dc)

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

