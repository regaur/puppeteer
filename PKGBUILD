# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=puppeteer
pkgver=1.7.0
pkgrel=4
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
install=${pkgname}.install

source=(
  'puppeteer-test'
  '00-local-userns.conf'
)

sha256sums=('a309758ae096e920b028be7c8efc2e992bb5c87e056b575a94103966602f279a'
            'd0d790d4c3d887b10b2b155b83a58a44980b9fa638f8c0f1faec0739dc0ef473')

pkgver () {
  npm view puppeteer@latest version
}

package () {
  install -Dm 755 -t "${pkgdir}/usr/bin" puppeteer-test
  install -Dm 655 -t "${pkgdir}/etc/sysctl.d" 00-local-userns.conf
  source "$HOME/.nvm/nvm.sh"
  nvm use 10.8.0
  local _npmdir="${pkgdir}/usr/lib/node_modules/"
  mkdir -p $_npmdir
  npm install -g --prefix "${pkgdir}/usr" puppeteer@${pkgver}

  # allow puppeteer to be required globally
  install -Dm 755 -d "${pkgdir}/usr/lib/node"
  ln -s /usr/lib/node_modules/puppeteer "${pkgdir}/usr/lib/node"
}
