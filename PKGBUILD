# Mantainer: Black_Codec <orso.f.regna@gmail.com>
# Contributor: Silvio Knizek <killermoehre@gmx.net>
# Contributor: Xavier Devlamynck <magicrhesus@ouranos.be>

pkgname=megafuse
pkgver=2
pkgrel=2
pkgdesc="A fuse based linux client for the MEGA cloud storage provider."
arch=('i686' 'x86_64')
license=('GPL2')
url="https://github.com/matteoserva/MegaFuse"
groups=()
depends=('crypto++' 'freeimage' 'readline' 'fuse')
optdepends=()
makedepends=()
source=(https://github.com/matteoserva/MegaFuse/archive/master.zip)
md5sums=('4688959ac6178ed3f3496db4fcc8ab21')


build() {
  cd $srcdir/MegaFuse-master/
  make
}

package() {
  cd $srcdir/MegaFuse-master/
  mkdir -p $srcdir/MegaFuse-master/usr/bin/
  mkdir -p $srcdir/MegaFuse-master/usr/share/MegaFuse/
  mv $srcdir/MegaFuse-master/MegaFuse $srcdir/MegaFuse-master/usr/bin/MegaFuse
  mv $srcdir/MegaFuse-master/megafuse.conf $srcdir/MegaFuse-master/usr/share/MegaFuse/megafuse.conf
  install -d $pkgdir/usr/bin
  install -m644 $srcdir/MegaFuse-master/usr/bin/* $pkgdir/usr/bin/
  install -d $pkgdir/usr/share/MegaFuse
  install -m644 $srcdir/MegaFuse-master/usr/share/MegaFuse/* $pkgdir/usr/share/MegaFuse/
  chmod +x $pkgdir/usr/bin/MegaFuse
}