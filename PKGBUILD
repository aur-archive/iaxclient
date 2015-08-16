# Contributor: Leonardo A. Gallego <leonardo@archlinux-es.org>
pkgname=iaxclient
pkgver=2.1beta3
pkgrel=1
pkgdesc="Multiplatform IAX library for creating telephony solutions that interoperate with Asterisk"
arch=('i686' 'x86_64')
url="http://iaxclient.wiki.sourceforge.net/"
license=('GPL')
groups=()
depends=('libvidcap')
makedepends=('libvidcap')
install=
source=(http://downloads.sourceforge.net/sourceforge/iaxclient/$pkgname-$pkgver.tar.gz)
md5sums=('47d54b9d5d48dc6aa1f6d7e506c72ba7')

build() {
  cd "$srcdir/$pkgname-$pkgver"

   sed -i 's|ffmpeg/avcodec.h|libavcodec/avcodec.h|' lib/codec_ffmpeg.c
  ./configure --prefix=/usr --disable-video --disable-clients --disable-gsmtest --disable-iax2test --with-wxdir=/usr/include/wx-2.8/wx --with-wx-config=/usr/bin/wx-config
  make || return 1
  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
