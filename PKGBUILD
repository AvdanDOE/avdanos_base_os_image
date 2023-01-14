pkgname=avdanos_base_image
pkgver="rel.$(date +%Y%m%d.%H%M).dp1"
pkgdesc="AvdanOS Base essential OS image files"
pkgrel="1"
arch=("x86_64")
depends=('filesystem' 'lsb-release' 'neofetch' 'cutefish-core' 'eww-git' 'zsh' 'harmonyos-sans-git' 'ttf-material-design-icons-git' 'xbindkeys' 'volnoti')

package() {
    rm -rf doebox
    git clone https://github.com/AvdanDOE/doebox/ -b v1lune-dp1
    mkdir -p "${pkgdir}/usr"
    mkdir -p "${pkgdir}/etc"
    mkdir -p "${pkgdir}/etc/avdanos"
    cp -r doebox/configuration/eww/dock ${pkgdir}/etc/avdanos
    cp -r doebox/configuration/eww/globalassets ${pkgdir}/etc/avdanos
    chmod -R +x ${pkgdir}/etc/avdanos/dock/scripts
    cp -r "${srcdir}/bin" "${pkgdir}/usr"
    echo "OS_VERSION=${pkgver}-${pkgrel}" > "${pkgdir}/etc/avdanos-release"
    echo "OS_RELEASE=priv-beta" >> "${pkgdir}/etc/avdanos-release"
    chmod -R +x "${pkgdir}/usr"
}
