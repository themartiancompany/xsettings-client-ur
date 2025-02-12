# SPDX-License-Identifier: AGPL-3.0

#    ----------------------------------------------------------------------
#    Copyright © 2025  Pellegrino Prevete
#
#    All rights reserved
#    ----------------------------------------------------------------------
#
#    This program is free software: you can redistribute it and/or modify
#    it under the terms of the GNU Affero General Public License as published by
#    the Free Software Foundation, either version 3 of the License, or
#    (at your option) any later version.
#
#    This program is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU Affero General Public License for more details.
#
#    You should have received a copy of the GNU Affero General Public License
#    along with this program.  If not, see <https://www.gnu.org/licenses/>.

# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Truocolo <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
# Maintainer: Pellegrino Prevete (dvorak) <pellegrinoprevete@gmail.com>
# Maintainer: Pellegrino Prevete (dvorak) <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>
# Maintainer: Sergej Pupykin <pupykin.s+arch@gmail.com>
# Contributor: Alois Belaska <lloyd@centrum.cz>

_os="$( \
  uname \
    -o)"
_pkg="matchbox"
_proj="yoctoproject"
_Pkgname="Xsettings-client"
pkgname=xsettings-client
pkgver=0.10
pkgrel=10
pkgdesc="Provides cross toolkit configuration settings such as theme parameters"
arch=(
  'x86_64'
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
if [[ "${_os}" == "Android" ]]; then
  depends+=(
    'xorgproto'
  )
fi
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
    "${srcdir}/${_Pkgname}-${pkgver}"
  ./configure \
    --prefix=/usr
  make
}

package() {
  cd \
    "${srcdir}/${_Pkgname}-${pkgver}"
  make \
    DESTDIR="${pkgdir}" \
    install
}
