pkgname=firmware-xiaomi-onclite
pkgver=1
pkgrel=0
_commit="8df0d3fe8d0902becdb23f582b61f921511d707a"
pkgdesc="Firmware files for Xiaomi Redmi 7"
url="https://postmarketos.org"
arch="aarch64"
license="proprietary"
depends="wcnss-wlan adsp-audio"
source="rosy-fw-$_commit.tar.gz::https://github.com/hiprivsid/postmarketos-vendor-xiaomi-onclite/archive/$_commit.tar.gz"
options="!strip !check !archcheck !spdx !tracedeps pmb:cross-native"

_fwdir="/lib/firmware/postmarketos"

package() {
	cd "$srcdir/postmarketos-vendor-xiaomi-onclite-$_commit"

	# ADSP firmware
	install -Dm0644 adsp/adsp.* -t "$pkgdir/$_fwdir"

	# Fingerprint firmware
	install -Dm0644 fingerprint/goodixfp.* -t "$pkgdir/$_fwdir"

	# GPU and video acceleration firmwares
	install -Dm0644 gpu/a530* -t "$pkgdir/$_fwdir/../qcom"
	install -Dm0644 gpu/a506_zap.* -t "$pkgdir/$_fwdir"
        install -Dm0644 venus/venus.* -t "$pkgdir/$_fwdir"

	# Modem firmware
	install -Dm0644 modem/mba.mbn -t "$pkgdir/$_fwdir"
	install -Dm0644 modem/modem.* -t "$pkgdir/$_fwdir"

	# Wifi/BT firmware
	install -Dm0644 wcnss/wcnss.* -t "$pkgdir/$_fwdir"
}

sha512sums=""
