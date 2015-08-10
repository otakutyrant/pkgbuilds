# Contributor: Mykola Dolhyi <0xb000@gmail.com>
pkgname=ignition-math
pkgver=2.2.2
pkgrel=1
pkgdesc="Math classes and functions for robot applications"
arch=('i686' 'x86_64')
url="http://ignitionrobotics.org/"
license=('Apache')
groups=('development')
depends=()
makedepends=('cmake' 'ruby-ronn' 'pkg-config>=0.28')
optdepends=()
provides=('ignition-math2')
conflicts=()
replaces=('ignition-math2')
#changelog=
source=("https://bitbucket.org/ignitionrobotics/ign-math/get/${pkgname}2_${pkgver}.tar.bz2")
#noextract=()
sha256sums=('e88db3ea1104330d009cd8d5f70e564296d2344a970fb964da9591fea884e2ab')
#validpgpkeys=()

_dir="ignitionrobotics-ign-math-de3837518b7d"

build() {
  cd "$srcdir/$_dir"

  mkdir -p build
  cd build

  # Configure build
  cmake .. -DCMAKE_BUILD_TYPE="Release" \
           -DCMAKE_INSTALL_PREFIX="/usr" \
           -DCMAKE_INSTALL_LIBDIR="lib" \
           -DENABLE_TESTS_COMPILATION:BOOL=False

  # Compile
  make
}

package() {
  cd "$srcdir/$_dir/build"
  make DESTDIR="$pkgdir/" install
}
