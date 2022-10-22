pkgname=avdanos_base_image
pkgver="rel.$(date +%Y%m%d.%H%M)"
pkgdesc="AvdanOS Base essential OS image files"
pkgrel="1"
arch=("x86_64")

package() {
    mkdir -p "${pkgdir}/usr/bin"
    mkdir -p "${pkgdir}/etc"
    cp "${srcdir}/avdanos-update" "${pkgdir}/usr/bin/avdanos-update"
    echo "$pkgver" > "${pkgdir}/etc/avdanos-release"
    chmod +x "${pkgdir}/usr/bin/avdanos-update"
}
