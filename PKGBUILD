##
#

_gitname=okasha
pkgname=python2-okasha-git
pkgver=0.2.4.r7.g77e0b4a
pkgrel=1
pkgdesc="okasha WSGI web fromwork"
arch=('any')
url="https://github.com/ojuba-org/okasha"
license=('Waqf v2')
makedepends=('git' 'python2' 'make')
depends=('python2' 'python2-paste' 'python2-lxml' 'kid')
source=("$pkgname::git+https://github.com/ojuba-org/${_gitname}.git")
md5sums=('SKIP')
provides=('okasha' 'python2-okasha')
replaces=('okasha' 'python2-okasha')
conflicts=('okasha' 'python2-okasha')

pkgver() {
  cd "${pkgname}"
  git describe --long --tags | sed -r 's/([^-]*-g)/r\1/;s/-/./g'
}

package() {
  cd "${pkgname}"
  find -exec sed -i 's:/usr/bin/python:/usr/bin/python2:g' {} \;
  python2 setup.py install --root=/"${pkgdir}"
}
