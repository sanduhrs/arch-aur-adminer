# Maintainer: Mario Finelli <mario at finel dot li>
# Contributor: Sabart Otto <seberm at gmail dot com>
# Contributor: Stefan Auditor <stefan.auditor@erdfisch.de>

pkgname=adminer
pkgver=4.2.4
pkgrel=3
pkgdesc="A full-featured MySQL management tool written in PHP."
arch=('any')
license=('Apache', 'GPL')
depends=('php')
optdepends=('mysql' 'apache' 'postgresql' 'sqlite')
url="https://www.adminer.org"
install=${pkgname}.install
source=("https://www.adminer.org/static/download/${pkgver}/${pkgname}-${pkgver}.php")
sha256sums=('ea21b95da1a2f66d26849160f3257823254663144e6b3b506c35160b70c7b3bd')

package() {
    cd "$srcdir"
    install -Dm0644 "${pkgname}-${pkgver}.php" \
        "$pkgdir/usr/share/webapps/$pkgname/index.php"

    # TODO: I don't really like this. What if someone is using nginx, for
    # example? Or doesn't care to have any configuration installed at all.
    # Consider removing.
    install -Dm0644 "../httpd-${pkgname}.conf" \
        "$pkgdir/etc/httpd/conf/extra/httpd-${pkgname}.conf"
}
