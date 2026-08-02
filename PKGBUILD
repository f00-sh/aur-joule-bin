pkgname=joule-bin
pkgver=0.1.8
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
sha256sums_x86_64=('deca74b02998fb23963dcc02b48ab176a4eeb7f0f2e77ad6f1abf85a22024ed9')
sha256sums_aarch64=('f4e62d238d01b29569241f233942a48e2810ebb57e6a876a852eab741551f8a8')
package() {
  cd "${srcdir}"
  root="$(find . -maxdepth 2 -type f -name joule | head -1 | xargs dirname)"
  install -Dm755 "${root}/joule" "${pkgdir}/usr/bin/joule"
}
