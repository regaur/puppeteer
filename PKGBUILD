# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=puppeteer
pkgver=1.7.0
pkgrel=1
pkgdesc="Remote control Chromium Browser from NodeJS via its debug API"
arch=('x86_64')
url=""
license=('MIT')
groups=()
depends=('nodejs=10.8.0-2')
makedepends=('npm')
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
source=()

pkgver () {
  npm view puppeteer@latest version
}

package () {
  source "$HOME/.nvm/nvm.sh"
  nvm use 10.8.0
  local _npmdir="${pkgdir}/usr/lib/node_modules/"
  mkdir -p $_npmdir
  npm install -g --prefix "${pkgdir}/usr" puppeteer@${pkgver}
}
