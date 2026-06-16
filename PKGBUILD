# Maintainer: callmetango
# Contributor: artist <artist@artixlinux.org>

pkgname=sonic-frameworks-io
pkgver=6.27.0
pkgrel=2
pkgdesc='Resource and network access abstraction'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-frameworks-io'
license=(LGPL-2.0-only LGPL-3.0-only)
depends=(acl
         libstdc++
         glibc
         karchive
         kbookmarks
         kcolorscheme
         kcompletion
         kconfig
         kcrash
         kdbusaddons
         ki18n
         kiconthemes
         kitemviews
         kjobwidgets
         kservice
         kwallet
         kwidgetsaddons
         libxml2
         libxslt
         qt6-base
         solid
         sonic-frameworks-core-addons
         sonic-frameworks-gui-addons
         sonic-frameworks-windowsystem
         util-linux-libs)
makedepends=(doxygen
             qt6-tools
             sonic-frameworks-cmake-modules
             sonic-frameworks-doctools)
optdepends=('audiocd-kio: for accessing audio CDs'
            'kded: proxy management and cookie storage'
            'kdoctools: for the help kioslave'
            'kio-extras: extra protocols support (sftp, fish and more)'
            'kio-fuse: to mount remote filesystems via FUSE'
            'switcheroo-control: hybrid GPU support')
conflicts=(kio)
provides=(kio)
replaces=(kio)
groups=(sonicde-frameworks)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('0949ce55ffdedafaaaaf75485966f594b84750be1879f7d63a114b5bba129196')

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DCMAKE_INSTALL_LIBDIR=lib \
    -DCMAKE_INSTALL_LIBEXECDIR=lib \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
