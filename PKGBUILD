pkgname=morphy-bin
pkgver=0.1.15
pkgrel=1
pkgdesc="Morphy — an infinite canvas for your AI agents"
arch=('x86_64')
url="https://get.appmorphy.com/"
license=('custom')
depends=(
  'gtk3'
  'libnotify'
  'nss'
  'libxss'
  'libxtst'
  'xdg-utils'
  'at-spi2-core'
  'util-linux-libs'
  'libsecret'
  'gcc-libs'
  'glibc'
)
optdepends=(
  'libappindicator-gtk3: system tray integration'
)
provides=('morphy')
conflicts=('morphy')
source=('https://github.com/casperaap/morphy-releases-/releases/download/v0.1.15/Morphy-0.1.15-amd64.deb')
sha256sums=('b5759652cae324875ab3f8c4c005fa5bd60068c840b63a511de1df073b4a51f0')

package() {
  bsdtar -xOf "$srcdir/Morphy.deb" data.tar.xz |
    bsdtar -xJf - -C "$pkgdir"

  install -d "$pkgdir/usr/bin"
  ln -s /opt/Morphy/morphy "$pkgdir/usr/bin/morphy"

  install -d "$pkgdir/usr/share/licenses/$pkgname"
  install -m644 "$pkgdir/opt/Morphy/LICENSE.txt" \
    "$pkgdir/usr/share/licenses/$pkgname/LICENSE.txt"
}
