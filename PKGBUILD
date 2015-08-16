# Maintainer: Rob Hunter <rhunter at darkhorse dot nu>

pkgname=mupen64plus-video-glide64
pkgver=2.0.0
pkgrel=1
pkgdesc="Video plugin for Mupen64Plus v2.0, based on the Glide64 plugin from Mupen64Plus 1.5."
arch=('i686' 'x86_64')
license=('GPL')
depends=("mupen64plus=2.0" "glew")
url=("https://bitbucket.org/wahrhaft/mupen64plus-video-glide64")
source=("https://bitbucket.org/wahrhaft/mupen64plus-video-glide64/downloads/mupen64plus-video-glide64-src-2.0.0.tar.gz")
md5sums=("9dee88ec3cac52e5ddc0357964459906")

build() {
    cd "$srcdir/$pkgname/projects/unix"
    make all || return 1
}

package() {
    cd "$srcdir/$pkgname/projects/unix"
    install -Dm644 mupen64plus-video-glide64.so $pkgdir/usr/lib/mupen64plus/mupen64plus-video-glide64.so

    cd "$srcdir/$pkgname/data"
    install -Dm644 Glide64.ini $pkgdir/usr/share/mupen64plus/Glide64.ini

    cd "$srcdir/$pkgname"
    install -Dm644 COPYING "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
