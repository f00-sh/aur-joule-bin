pkgname=joule-bin
pkgver=0.1.6
pkgrel=1
pkgdesc="joule prebuilt"
arch=('x86_64' 'aarch64')
url="https://joule.f00.sh/"
license=('MIT')
provides=('joule')
conflicts=('joule')
options=('!strip')
source_x86_64=("https://github.com/f00-sh/joule/releases/download/v${pkgver}/joule-${pkgver}-linux-x86_64.tar.gz")
source_aarch64=("https://github.com/f00-sh/joule/releases/download/v${pkgver}/joule-${pkgver}-linux-aarch64.tar.gz")
sha256sums_x86_64=('582c3d0b5ff09d045db7c4bd98ec1be30b112ed6958269b1b997e90d712b35c7')
sha256sums_aarch64=('2bfb0c5acfbd75d2842b2222c01b88fec0c090584da7014d9d0accd8e2932bac')
package() {
  cd "${srcdir}"
  root="$(find . -maxdepth 2 -type f -name joule | head -1 | xargs dirname)"
  install -Dm755 "${root}/joule" "${pkgdir}/usr/bin/joule"
}
