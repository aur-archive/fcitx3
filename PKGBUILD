pkgname=fcitx3
pkgver=3.6.4
pkgrel=1
pkgdesc='Free Chinese Input Toy of X - Input Method Server for X window system (XIM)'
arch=('i686' 'x86_64')
url='http://www.fcitx.org/'
license=('GPL')
depends=('libxft' 'libxpm' 'libxtst' 'dbus-core')
provides=('fcitx')
conflicts=('fcitx')
source=("http://fcitx.googlecode.com/files/fcitx-$pkgver.tar.gz")
md5sums=('f4dc284ca4d1bd74374b49361269f644')

build() {
	cd "$srcdir/fcitx-$pkgver"

	sed -i 's/python/python2/' tools/winmb2fcitx.py

	./autogen.sh
	./configure --prefix=/usr \
	--disable-tray \
	--disable-recording \
	--disable-dbus

	make LDFLAGS=-ldl
}

package() {
	cd "$srcdir/fcitx-$pkgver"

	make DESTDIR="$pkgdir" install
}
