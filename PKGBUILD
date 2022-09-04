#!/bin/bash

# Created from the original PKGBUILD by Caleb Maclennan <caleb@alerque.com>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/python-statmake/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/python-statmake/discussions>

_langname="python"
_relname="statmake"

pkgname="${_langname}-${_relname}"
pkgver=0.4.1
pkgrel=1
pkgdesc="A utility to dump, merge and compile Visual TrueType data in UFO3 with FontTools"
arch=(
  "any"
)
url="https://github.com/daltonmaag/statmake"
license=(
  "MIT"
)
depends=(
  "python"
  "python-attrs"
  "python-cattrs"
  "python-fonttools" # optdepends of fonttools required for [ufo]
  "python-fs"
)
makedepends=(
  "python-setuptools"
)
replaces=(
  "statmake"
)
_tarname="${_relname}-${pkgver}"
source=(
  "https://files.pythonhosted.org/packages/source/${_relname::1}/${_relname}/$_tarname.tar.gz"
)
sha512sums=(
  "822382b16bf1f9d72beb4648eb8c8e70343bad75ab1030412adb7e31cac454c6dcb359beb327fe9bd3eaac25845b51e3b99a49bee5471c0325917b4d53a65379"
)

build() {

  cd "${_tarname}"

  python setup.py build
}

package() {

  cd "${_tarname}"

  python setup.py install --root="${pkgdir}" --optimize=1 --skip-build

  install -Dm0644 -t "${pkgdir}/usr/share/licenses/${pkgname}/" LICENSE
}
