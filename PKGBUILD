# Maintainer: Dan Johansen <strit@manjaro.org>
# Maintainer : Max Fierke <max@maxfierke.com>

pkgname=clockworkpi-a06-post-install
pkgver=20$(date +%y%m%d)
pkgrel=1
pkgdesc="clockworkPI DevTerm A06 post install files"
arch=('any')
url="https://github.com/maxfierke/clockworkpi-a06-alarm"
license=('GPL')
install=${pkgname}.install
source=('10-monitor.conf')
md5sums=('0939a3e65eca3ca2e8bd8f4f843eed47')

package() {
    echo "Modifying clockworkpi-a06 specific files..."

    install -Dm644 "${srcdir}/10-monitor.conf"  "${pkgdir}/etc/X11/xorg.conf.d/10-monitor.conf"
}
