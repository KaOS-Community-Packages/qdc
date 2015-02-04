_pkgname=qrae
pkgname=qrae
pkgver=0.4.2
pkgrel=1
pkgdesc="Spanish Royal Academy dictionary desktop client"
arch=('x86_64')
url="https://build.opensuse.org/source/KDE:Extra/qrae"
license=('GPL')
depends=('qt5-base')
makedepends=('git' 'make')
source=(https://build.opensuse.org/source/KDE:Extra/qrae/${pkgname}-${pkgver}.tar.bz2)
md5sums=('4995a5e4c68ff7d19591013853fef8f7')

build() {

  cd "$srcdir/${_pkgname}"
  /usr/lib/qt5/bin/qmake qrae.pro DESTDIR="$srcdir/${_pkgname}"
  
  make
}

package() {
  install -m755 -d ${pkgdir}/usr/{bin,share/{applications,pixmaps,doc/qrae}}

  install -m755 "$srcdir/${_pkgname}"/qrae "$pkgdir"/usr/bin/
  install -m644 "$srcdir/${_pkgname}"/qrae.png "$pkgdir"/usr/share/pixmaps/
  install -m644 "$srcdir/${_pkgname}"/qrae.desktop "$pkgdir"/usr/share/applications/
  install -m644 "$srcdir/${_pkgname}"/{ChangeLog,COPYING,gpl-2.0.txt,gpl-3.0.txt} "$pkgdir"/usr/share/doc/qrae/
}
