# Maintainer: Sebastian Jensen <gonx@gonx.dk>
pkgname=cloudflare-ddns-networkd-git
pkgver=r7.c29588f
pkgrel=1
pkgdesc="networkd-dispatcher script to update DDNS when interface goes routeable"
arch=(any)
url="https://github.com/gonX/cloudflare-ddns-merlinwrt"
license=('MIT')
depends=('curl' 'sh')
makedepends=('git')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
backup=(etc/cloudflare-ddns.conf)
source=('cloudflare-ddns-networkd::git+https://github.com/gonX/cloudflare-ddns-merlinwrt.git#branch=networkd-dispatcher')
noextract=()
md5sums=('SKIP')

pkgver() {
    cd "$srcdir/${pkgname%-git}"

    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
    cd "$srcdir/${pkgname%-git}"
    sed -i 's!$(dirname "$0")/ddns.config!/etc/cloudflare-ddns.conf!' ddns-start
}

package() {
    cd "$srcdir/${pkgname%-git}"
    install -Dm744 ddns-start  "$pkgdir"/usr/lib/networkd-dispatcher/routable.d/90-ddns
    install -Dm600 ddns.config "$pkgdir"/etc/cloudflare-ddns.conf
}
