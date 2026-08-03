# Maintainer: William Theesfeld <william@theesfeld.net>
pkgname=joule-bin
pkgver=0.1.10
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
sha256sums_x86_64=('07d9b82abd1ddd3844d5ffeb239f1d2a205ca659d437c8e1c6237697bc712662')
sha256sums_aarch64=('26c98d00cca21cd583e6e4d6dc90f5d9cd5e4410f22f5ce992cc8c5cd33f0d7f')
package() {
  cd "${srcdir}"
  root="$(find . -maxdepth 2 -type f -name joule | head -1 | xargs dirname)"
  install -Dm755 "${root}/joule" "${pkgdir}/usr/bin/joule"
}
