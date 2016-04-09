pkgname=qdc
pkgver=1.0.0
pkgrel=1
pkgdesc="Spanish Royal Academy dictionary desktop client"
arch=('x86_64')
url="https://github.com/javierllorente/qdc/"
license=('GPL')
depends=('qt5-base' 'qt5-webkit')
makedepends=('make' 'qt5-tools')
source=(https://github.com/javierllorente/qdc/archive/v${pkgver}.tar.gz)
md5sums=('9b9d412a9b36d5eaa9f84191b71cc2e3')

build() {
  cd "$srcdir/${pkgname}-${pkgver}"
  qmake-qt5 ${pkgname}.pro DESTDIR="$srcdir/${pkgname}"
  make
}

package() {
  install -m755 -d ${pkgdir}/usr/{bin,share/{applications,pixmaps,doc/${pkgname}}}

  install -m755 "$srcdir/${pkgname}"/${pkgname} "$pkgdir"/usr/bin/
  install -m644 "$srcdir/${pkgname}-${pkgver}"/icons/${pkgname}.png "$pkgdir"/usr/share/pixmaps/
  install -m644 "$srcdir/${pkgname}-${pkgver}"/${pkgname}.desktop "$pkgdir"/usr/share/applications/
  install -m644 "$srcdir/${pkgname}-${pkgver}"/{ChangeLog,COPYING,gpl-2.0.txt,gpl-3.0.txt} "$pkgdir"/usr/share/doc/${pkgname}/
}
