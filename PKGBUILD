pkgname=scid
pkgver=5.0.2
pkgrel=1
pkgdesc="A Free Chess Database Application"
url="http://scid.sourceforge.net"
arch=('x86_64')
license=('GPL')
depends=('tk')

source=("https://github.com/benini/scid/archive/refs/tags/v${pkgver}.tar.gz"
        'scid.desktop')
sha256sums=('54b1b3c66810d806464966cafd73f0afa2aa39bd2e17549ebf1d12f659e46301'
            '85fad4977ebe7992163be9d98a5d6ddfb0cf5a69a91c6f8e1ee712c49e9a0ee4')


build() {

  cd ${srcdir}/scid-${pkgver}
  ./configure BINDIR=/usr/bin SHAREDIR=/usr/share/scid SCIDFLAGS="$LDFLAGS"
  make
}

package () {

  cd $srcdir/${pkgname}-${pkgver}
  make DESTDIR=$pkgdir install

  msg "Desktop file-icon"
  install -Dm644 $srcdir/scid.desktop $pkgdir/usr/share/applications/scid.desktop
  install -Dm644 ${srcdir}/scid-${pkgver}/resources/svg/scid.ico $pkgdir/usr/share/scid/scid.ico

}

