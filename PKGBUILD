# Maintainer: Chirantan Ekbote <chirantan.ekbote at gmail.com>
# Contributor: Eric Anderson <ejona86 at gmail.com>
# Contributor: Pierre DOUCET <pierre at equinoxefr.org>
pkgname=openscad
pkgver=2013.06
pkgrel=2
pkgdesc="Software for creating solid 3D CAD objects."
arch=('i686' 'x86_64')
license=('GPLv2')
url="http://openscad.org/"
source=("https://openscad.googlecode.com/files/$pkgname-$pkgver.src.tar.gz"
    "openscad.png::http://upload.wikimedia.org/wikipedia/commons/thumb/9/97/OpenSCAD-logo.png/128px-OpenSCAD-logo.png"
    "openscad.desktop")
changelog=CHANGELOG
makedepends=('eigen')
depends=( 'qt4' 'cgal' 'opencsg' )
md5sums=('b7b5faecdffc41e28cdf0c1162299de7'
    '7182ff03b6babdb60b57b8adf06a805b'
    '4ebc85c8dbf91aefdd80fd2285909c82')

build() {
    cd "$srcdir/$pkgname-$pkgver"
    qmake-qt4 PREFIX="/usr"
    make
}

package() {
    cd "$srcdir/$pkgname-$pkgver"
    make INSTALL_ROOT="$pkgdir" install
    install -D -m644 "$srcdir/$pkgname.desktop" "$pkgdir/usr/share/applications/$pkgname.desktop"
    install -D -m644 "$srcdir/$pkgname.png" "$pkgdir/usr/share/pixmaps/$pkgname.png"
}
