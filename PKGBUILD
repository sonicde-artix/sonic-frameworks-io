# Maintainer: callmetango
# Contributor: artist <artist@artixlinux.org>

pkgname=sonic-frameworks-io
pkgver=6.26.0
pkgrel=1
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
         kguiaddons
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
         sonic-frameworks-windowsystem
         util-linux-libs)
makedepends=(doxygen
             extra-cmake-modules
             kdoctools
             qt6-tools)
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
sha256sums=('1f9a1fce613a7f7ee34480194269a0ea75ec4c4b098253781e4c451699031115')

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DCMAKE_INSTALL_LIBEXECDIR=lib \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
