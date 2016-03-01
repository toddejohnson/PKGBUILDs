# Maintainer: Michael Schubert <mschu.dev at gmail>
pkgname=python-llvmlite
pkgver=0.9.0
pkgrel=1
pkgdesc="Lightweight LLVM python binding for writing JIT compilers"
url="http://numba.pydata.org/"
arch=('i686' 'x86_64')
license=('BSD')
depends=('python' 'llvm>=3.7.0' 'llvm<3.8.0')
makedepends=('cython')
source=("https://github.com/numba/llvmlite/archive/v$pkgver.tar.gz")
md5sums=('b2b7071b20731b084ef761a459bf3750')

build() {
  cd "$srcdir/llvmlite-$pkgver"
  sed -i "s/-lLLVMOProfileJIT//" ffi/Makefile.linux
  python setup.py build
}

package() {
  cd "$srcdir/llvmlite-$pkgver"
  python setup.py install --skip-build --prefix=/usr --root="$pkgdir" --optimize=1
}
