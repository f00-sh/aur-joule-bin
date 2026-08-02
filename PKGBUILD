# Maintainer: f00 joule
pkgname=joule-bin
pkgver=0.1.5
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
sha256sums_x86_64=('324f4afca063c7dbbb9d71c6b03fff6418818521a15a79d04b57e80c6fab909e')
sha256sums_aarch64=('e787b2506f8b776faf314cd0f38088412b7c35854de26ac36d2939fc5c15dc50')
package() {
  cd "${srcdir}"
  root="$(find . -maxdepth 2 -type f -name joule | head -1 | xargs dirname)"
  install -Dm755 "${root}/joule" "${pkgdir}/usr/bin/joule"
}
