#Maintainer: Stéphane Marguet (Stemp) <smarguet à gmail point com>
#Contributor: Gergely Tamas <dice@mfa.kfki.hu>
pkgname=dvbstream
pkgver=0.8
pkgrel=2
pkgdesc="RTP-ize a DVB transport stream."
url="http://sourceforge.net/projects/dvbtools/"
license=('GPL')
changelog=ChangeLog
depends=('glibc')
arch=(i686 x86_64)
source=(http://www.orcas.net/dvbstream/$pkgname-$pkgver.tar.bz2 dumprtp.1 dvbstream.1 rtpfeed.1 ts_filter.1)
md5sums=('09b1eba583c8b0ba5d04bf5cd2dd58a0' '89904079c0893ed2755582ac15135f3e'\
         '39db6f4875fca38676497f7a95f74c97' '93f231c87856e29308adb40ba7936a8e'\
         '797f52c6db4d0ded079cb2bc5f6cfee9')

build() {
  cd $srcdir/$pkgname
  make || return 1
  mkdir -p $pkgdir/usr/{bin,man/man1}
  for i in dumprtp dvbstream rtpfeed ts_filter; do
    install -m 755 $i $pkgdir/usr/bin
    install -m 644 $srcdir/${i}.1 $pkgdir/usr/man/man1
  done
}
