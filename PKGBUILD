# Maintainer: f00 joule <william@theesfeld.net>
# Binary package from GitHub Releases (f00-sh/joule)

pkgname=joule-bin
pkgver=0.1.2
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
sha256sums_x86_64=('376ab1b59a97d8a620004a925ea468b9a91cdc6876f0997bf14d3e2eb26aa787')
sha256sums_aarch64=('e254e69b462c7737026826d8a7d895838266021441c5233bfaaf0dc68577f7f9')

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
