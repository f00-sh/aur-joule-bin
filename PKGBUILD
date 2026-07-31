# Maintainer: f00 joule <william@theesfeld.net>
# Binary package from GitHub Releases (f00-sh/joule)

pkgname=joule-bin
pkgver=0.1.3
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
sha256sums_x86_64=('5f77122c25f0eb83662329033e100a3919bc14af059657cc877a08ea1542470b')
sha256sums_aarch64=('337af68f79a5eb70b3c9e48f57fc45f75a09dd40b3c57d1116bff215ff7062e8')

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
