# Maintainer: Sam Van der Borght <sam@king-foo.be>
pkgname=valentina-vphp54-beta
pkgver=current
pkgrel=2
pkgdesc="Valentina database PHP 5.4 extension, required for connecting to valentina databases through PHP"
arch=('x86_64')
url="http://www.valentina-db.com/download/beta/"
license=('unknown')
depends=('libpng12')
makedepends=('rpmextract')
options=('emptydirs')
source=("http://www.valentina-db.com/download/beta/5.0b66/linux_64/vphp54_standalone_x64_5_lin.rpm")
md5sums=('b209779516c64e413fd19559083c7588')
package() {
  cd "$pkgdir"
  rpmextract.sh ../vphp54_standalone_x64_5_lin.rpm
  rm -rf "$srcdir/opt/VPHP_Standalone54/vcomponents/libz.so*"
  rm -rf "$srcdir/opt/VPHP_Standalone54/vcomponents/libicu*.so.48"
  rm -rf "$srcdir/opt/VPHP_Standalone54/vcomponents/libtiff.so.4*"
  echo "Create a file valentina.ini in your PHP config dir (eg. /etc/php/conf.d/)."
  echo "Add the following line to it: extension=/opt/VPHP_Standalone54/php54_valentina_standalone.so"
}
post_install() {
  ldconfig
}
