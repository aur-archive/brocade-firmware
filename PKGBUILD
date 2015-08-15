# Maintainer: Spider.007 <archPackage@spider007.net>
# Contributor: Spider.007 <archPackage@spider007.net>
packager="Spider.007 <archPackage@spider007.net>"
pkgname=brocade-firmware
pkgver=3.2.21.0
pkgrel=2
pkgdesc="Firmware for brocade adapters"
url="http://www.brocade.com/services-support/drivers-downloads/adapters/Linux.page"
install=mkinitcpio.install
groups=modules
license='custom'
# This source downloaded from http://esd.brocade.com/s/documents/downloads/HBA/Linux/Drivers/NOARCH/bfa_fw_update_to_v$pkgver.tgz but no direct link is allowed
source=(LICENSE "bfa_fw_update_to_v$pkgver.tgz")
arch=('any')
md5sums=('3d801d41addad546d9b8a58885bc2fa9'
         'c5211e8f05ed23267ac98a4819558ea6')

package() {
	install -D -m644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"

	cd $srcdir/bfa_fw_update_to_v$pkgver/
	mkdir -p $pkgdir/lib/firmware/
	cp *.bin "${pkgdir}/lib/firmware/"
	# Symlinks to hardcoded names in drivers/net/ethernet/brocade/bna/cna.h
	ln -s ct2fw-3.2.1.0.bin "${pkgdir}/lib/firmware/ct2fw-3.1.0.0.bin"
	ln -s ctfw-3.2.1.0.bin "${pkgdir}/lib/firmware/ctfw-3.1.0.0.bin"
}
