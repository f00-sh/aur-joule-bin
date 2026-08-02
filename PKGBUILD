# Maintainer: f00 joule <william@theesfeld.net>
pkgname=joule-bin
pkgver=0.1.4
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
sha256sums_x86_64=('ea5a485bd546a9f7bfec1fac3ac5a10ac15c0cf610913a88550cced3ac6c630b')
sha256sums_aarch64=('ea21451547027732c107c9bfcd8303de1ba33b95cd942c4cc5700708206440ea')

package() {
  cd "${srcdir}"
  local root
  root="$(find . -maxdepth 2 -type f -name joule | head -1 | xargs dirname)"
  install -Dm755 "${root}/joule" "${pkgdir}/usr/bin/joule"
  if [[ -f "${root}/man/joule.1" ]]; then
    install -Dm644 "${root}/man/joule.1" "${pkgdir}/usr/share/man/man1/joule.1"
  elif [[ -f "${root}/man/joule.1.md" ]]; then
    install -Dm644 "${root}/man/joule.1.md" "${pkgdir}/usr/share/doc/joule/joule.1.md"
  fi
  if [[ -f "${root}/LICENSE" ]]; then
    install -Dm644 "${root}/LICENSE" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  fi
}
