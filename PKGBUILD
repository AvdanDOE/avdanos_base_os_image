pkgname=avdanos_base_image
pkgver="rel.$(date +%Y%m%d.%H%M)"
pkgdesc="AvdanOS Base essential OS image files"
pkgrel="1"
arch=("x86_64")

package() {
    rm -rf doebox
    git clone https://github.com/AvdanDOE/doebox/ -b v1lune-dp1
    mkdir -p "${pkgdir}/usr/bin"
    mkdir -p "${pkgdir}/etc"
    mkdir -p "${pkgdir}/etc/avdanos"
    mv doebox/configuration/eww/dock ${pkgdir}/etc/avdanos
    cp "${srcdir}/avdanos-update" "${pkgdir}/usr/bin/avdanos-update"
    echo "OS_VERSION=${pkgver}-${pkgrel}" > "${pkgdir}/etc/avdanos-release"
    echo "OS_RELEASE=priv-beta" >> "${pkgdir}/etc/avdanos-release"
    chmod +x "${pkgdir}/usr/bin/avdanos-update"
}
