# Maintainer: Aaron DeVore <aaron.devore@gmail.com>
# Contributor:  tocer <tocer.deng@gmail.com>
# Contributor: Piotr Beling <qwak@stud.ics.p.lodz.pl>
# Contributor: Douglas Soares de Andrade <dsandrade@gmail.com>

pkgname=python3-xlrd
_rev=f5846f7
# Commit count: git rev-list --count <tag>.."$_rev"
pkgver="0.8.0+22+g${_rev}"
pkgrel=1
pkgdesc="A library for developers to use to extract data from Microsoft Excel (tm) spreadsheet files."
url="https://github.com/python-excel/xlrd/pull/2"
makedepends=('python3')
provides=("python-xlrd")
source=("https://github.com/takluyver/xlrd/tarball/$_rev")
md5sums=('31b5f64f7f0cfe83cba2a05f33267d8d')
arch=('any')
license=('BSD')

package() {
  cd "$srcdir/takluyver-xlrd-$_rev"
  python3 setup.py install --root="$pkgdir"
  local docdir
  docdir="$pkgdir/usr/share/doc/$pkgname/"
  install -D -m644 "xlrd/licences.py" \
    "$pkgdir/usr/share/licenses/$pkgname/licences.py"
  
  # This script is not ported to Python 3 and would conflict with the version
  # provided in the Python 2 package anyway
  rm "$pkgdir/usr/bin/runxlrd.py"
  
  mkdir -p "$docdir"
  cp -a xlrd/doc/* "$docdir"
}
