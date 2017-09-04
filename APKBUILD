# Contributor: Michael Eddington <meddington+alpine@gmail.com>
# Maintainer: Michael Eddington <meddington+alpine@gmail.com>
pkgname=py-protobuf
_pkgname=protobuf
pkgver=3.3.0
pkgrel=0
pkgdesc="Protocol Buffers are Google’s data interchange format."
url="https://pypi.python.org/pypi/protobuf"
arch="all"
license="New BSD License"
depends="python"
depends_dev=""
makedepends="python-dev py-setuptools"
install=""
subpackages=""
source="https://pypi.python.org/packages/source/${_pkgname:0:1}/$_pkgname/$_pkgname-$pkgver.tar.gz"

_builddir="$srcdir/$_pkgname-$pkgver"
prepare() {
	local i
	cd "$_builddir"
	for i in $source; do
		case $i in
		*.patch) msg $i; patch -p1 -i "$srcdir"/$i || return 1;;
		esac
	done
}

build() {
	cd "$_builddir"
	python setup.py build || return 1
}

package() {
	cd "$_builddir"
	python setup.py install --prefix=/usr --root="$pkgdir" || return 1
}

md5sums="27941e8e42e83d5183605054576882dd  protobuf-3.3.0.tar.gz"
sha256sums="1cbcee2c45773f57cb6de7ee0eceb97f92b9b69c0178305509b162c0160c1f04  protobuf-3.3.0.tar.gz"
sha512sums="43cca936aa6da55595f1abcb22e698d914b1019a0ab09de972f6d0f3dab635d75f6ea8ad76cdcbf37d861fa33128918ca109ed01ec38545f9ee1ef6cfc7eddcf  protobuf-3.3.0.tar.gz"
