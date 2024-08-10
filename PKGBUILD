# Maintainer: Pierre Schmitz <pierre@archlinux.de>
# Maintainer: Bartłomiej Piotrowski <bpiotrowski@archlinux.org>

pkgname=archlinux-lcpu-keyring
pkgver=20240810
pkgrel=1
pkgdesc='Loongarch64 PGP keyring'
arch=('any')
url='https://gitlab.archlinux.org/archlinux/archlinux-keyring/'
license=('GPL-3.0-or-later')
install=$pkgname.install
depends=('pacman')
makedepends=('git' 'python' 'sequoia-sq' 'pkgconf' 'systemd')
checkdepends=('python-coverage' 'python-pytest')
source=("archlinux-lcpu-keyring::git+https://github.com/lcpu-club/archlinux-lcpu-keyring.git#tag=${pkgver}")
#deleted signed option
#sha256sums=('139bb9d1bf831b35e4819fdec6706dcfee046f6f7d704b0f742742673f4d5a20')
validpgpkeys=(archlinux-lcpu.gpg)

build() {
  cd archlinux-lcpu-keyring/

  make build
}

check() {
  cd archlinux-lcpu-keyring/

  make check
}

package() {
  cd archlinux-lcpu-keyring/

  make PREFIX='/usr' DESTDIR="${pkgdir}" install
}
