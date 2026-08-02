pkgname=joule-bin
pkgver=0.1.7
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
sha256sums_x86_64=('a62b701ba4d79f2481bf68721ddb713fd7fb61e7754133e36a4422c1935a599a')
sha256sums_aarch64=('f55bdb89ddc3a20b047c6efd4544941fd7307d03ad2971abd9fb57d7c86d4249')
package() {
  cd "${srcdir}"
  root="$(find . -maxdepth 2 -type f -name joule | head -1 | xargs dirname)"
  install -Dm755 "${root}/joule" "${pkgdir}/usr/bin/joule"
}
