#
# Maintainer: Sergej Pupykin <pupykin.s+arch@gmail.com>
# Contributor: Alois Belaska <lloyd@centrum.cz>

_pkg="matchbox"
_proj="yoctoproject"
_Pkgname="Xsettings-client"
pkgname=xsettings-client
pkgver=0.10
pkgrel=10
pkgdesc="Provides cross toolkit configuration settings such as theme parameters"
arch=(
  'x86_64'
  $CARCH
  'arm'
  'aarch64'
  'armv7l'
  'mips'
  'pentium4'
  'powerpc'
)
license=(
  'GPL'
)
url="http://${_pkg}-project.org"
depends=(
  'libx11'
)
_http="https://downloads.${_proj}.org"
_ns="releases"
_url="${_http}/${_ns}/${_pkg}"
source=(
  "${_url}/optional-dependencies/${_Pkgname}-${pkgver}.tar.gz"
)
sha512sums=(
  '051eaafa3410f82afea8f5909e5ef46548737f5b7bb3cb9c31262426ebc8e39ce4e84cfa76629cfb6b608fc764b2bbc3e7345a0e8e4257c7f6ea640c3b419634'
)

build() {
  cd \
    "${srcdir}/${_Pkg}-${pkgver}"
  ./configure \
    --prefix=/usr
  make
}

package() {
  cd \
    "${srcdir}/${_Pkg}-${pkgver}"
  make \
    DESTDIR="${pkgdir}" \
    install
}
