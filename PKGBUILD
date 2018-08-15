# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=puppeteer
pkgver=1.7.0
pkgrel=1
pkgdesc="Remote control Chromium Browser from NodeJS via its debug API"
arch=('x86_64')
url=""
license=('MIT')
groups=()

depends=(
  'nodejs=10.8.0-2'
  'alsa-lib'
  'dbus'
  'desktop-file-utils'
  'ffmpeg'
  'flac'
  'fontconfig'
  'freetype2'
  'gtk3'
  'harfbuzz'
  'hicolor-icon-theme'
  'icu'
  'json-glib'
  'libcups'
  'libgcrypt'
  'libjpeg-turbo'
  'libpulse'
  'libwebp'
  'libxml2'
  'libxslt'
  'libxss'
  'minizip'
  'nss'
  'opus'
  'pciutils'
  're2'
  'snappy'
  'systemd'
  'noto-fonts'
  'xdg-utils'
)

makedepends=('npm')
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
source=('puppeteer-test')

sha256sums=('24c7c8b2f33e537b9f3cf38f215592e2336f494ba0f64ebc644ed666807553cf')

pkgver () {
  npm view puppeteer@latest version
}

package () {
  install -Dm 755 -t "${pkgdir}/usr/bin" puppeteer-test
  source "$HOME/.nvm/nvm.sh"
  nvm use 10.8.0
  local _npmdir="${pkgdir}/usr/lib/node_modules/"
  mkdir -p $_npmdir
  npm install -g --prefix "${pkgdir}/usr" puppeteer@${pkgver}
}
