# Maintainer: William Theesfeld <william@theesfeld.net>
pkgname=joule-bin
pkgver=0.1.9
pkgrel=1
pkgdesc="Donate idle compute, earn millijoules, use open-weight AI (prebuilt binary)"
arch=('x86_64' 'aarch64')
url="https://joule.f00.sh/"
license=('MIT')
provides=('joule')
conflicts=('joule')
options=('!strip')
source_x86_64=("https://github.com/f00-sh/joule/releases/download/v${pkgver}/joule-${pkgver}-linux-x86_64.tar.gz")
source_aarch64=("https://github.com/f00-sh/joule/releases/download/v${pkgver}/joule-${pkgver}-linux-aarch64.tar.gz")
sha256sums_x86_64=('856baa9e720dbe5728f10aa4fdb41e6aeccb088c2efd8aeb8180777bb91a011c')
sha256sums_aarch64=('0d64f90d8e2307ff07e1cd001f020697a070504a474aa7b01f37f2b0a5164cd9')
package() {
  cd "${srcdir}"
  root="$(find . -maxdepth 2 -type f -name joule | head -1 | xargs dirname)"
  install -Dm755 "${root}/joule" "${pkgdir}/usr/bin/joule"
}
