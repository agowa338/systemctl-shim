pkgname=systemctl-shim
pkgver=0.0.1
pkgrel=0
pkgdesc="Adds systemctl shim to OS with openrc"
url="https://github.com/agowa338/systemctl-shim"
arch="noarch"
license="GPL-3.0-or-later"
makedepends="git"
depends="openrc"
options="!check"  # no tests provided

_giturl="https://github.com/agowa338/systemctl-shim.git"

prepare() {
        default_prepare
        # Use tarball instead of git for release
        # https://wiki.alpinelinux.org/wiki/Creating_an_Alpine_package#APKBUILD_variables.2Ffunctions
        git clone "$_giturl" "$srcdir/$pkgname"
}

package() {
        mkdir -p "$pkgdir/usr/bin/"
        install -o root -g root -m755 "$srcdir/$pkgname/systemctl-shim.sh" "$pkgdir/usr/bin/systemctl"
}
