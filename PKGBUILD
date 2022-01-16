# Maintainer: Dan Johansen <strit@manjaro.org>
# Maintainer: Max Fierke <max@maxfierke.com>

pkgname=clockworkpi-a06-post-install
pkgver=20$(date +%y%m%d)
pkgrel=1
pkgdesc="ClockworkPi DevTerm A06 post install files"
arch=('any')
url="https://manjaro.org"
license=('GPL')
install=${pkgname}.install
optdepends=('alsa-ucm-conf>=1.2.6.2')
source=(
    '10-monitor.conf'
    'es8388.conf'
    'HiFi.conf'
)
sha256sums=('11243c7f9746b7bb23740f50ef2df56a208795e19df2cda659b530c3fc3f9755'
            'bf65ae20d52bc035889c1c940ab939dc8b9d086d4d03d65a53415ed372acb287'
            'd4f87eec9a0f8c041f64e5825e065ba089a2ae1e2320948d0665d385e24d7558')

package() {
    echo "Modifying clockworkpi-a06 specific files..."

    # Install X rotation fix as it does not read panel orientation from kernel
    install -Dm644 "${srcdir}/10-monitor.conf" "${pkgdir}/etc/X11/xorg.conf.d/10-monitor.conf"

    # Install alsa-ucm-conf profile for DevTerm A06
    mkdir -p "${pkgdir}/usr/share/alsa/ucm2/Rockchip/es8388"
    install -Dm644 "${srcdir}/es8388.conf" "${pkgdir}/usr/share/alsa/ucm2/Rockchip/es8388/es8388.conf"
    install -Dm644 "${srcdir}/HiFi.conf" "${pkgdir}/usr/share/alsa/ucm2/Rockchip/es8388/HiFi.conf"

    mkdir -p "${pkgdir}"/usr/share/alsa/ucm2/conf.d/simple-card
    ln -sfv /usr/share/alsa/ucm2/Rockchip/es8388/es8388.conf \
            "${pkgdir}"/usr/share/alsa/ucm2/conf.d/simple-card/rockchip,es8388-codec.conf
}
