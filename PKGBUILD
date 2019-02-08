# Maintainer: Jan Boelsche <jan@lagomorph.de>

pkgname=tre-parts-git
pkgver=1.0.1.r2.3d2348d
pkgrel=1
pkgdesc="Composite messages"
arch=('any')
url=""
license=('AGPLv3')
groups=()
depends=('scuttlebot')
depends=('ssb-revisions-git')
makedepends=('git' 'npm')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
replaces=()
backup=()
options=()

source=("git+ssh://git@github.com/regular/${pkgname%-git}.git")

sha256sums=('SKIP')

pkgver() {
	cd "$srcdir/${pkgname%-git}"
  printf "%s.r%s.%s" "$(node -e 'console.log(require("./package.json").version)')" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package () {
	cd "$srcdir/${pkgname%-git}"
  source "$HOME/.nvm/nvm.sh"
  nvm use 10.8.0
  local _npmdir="${pkgdir}/usr/lib/node_modules/"
  mkdir -p $_npmdir
  npm install -g --prefix "${pkgdir}/usr" regular/${pkgname%-git}
}
