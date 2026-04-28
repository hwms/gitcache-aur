# Maintainer: Mathias Seidler <seishin@gmail.com>

pkgname=gitcache
pkgver=1.0.33
pkgrel=3
pkgdesc='Local cache for git repositories to speed up working with large repositories and multiple clones'
arch=('any')
url='https://github.com/seeraven/gitcache'
license=('BSD-3-Clause')
install="${pkgname}.install"
depends=(
  'git'
  'python'
  'python-coloredlogs'
  'python-portalocker'
  'python-pytimeparse'
)
makedepends=(
  'git'
  'python-build'
  'python-installer'
  'python-setuptools'
  'python-wheel'
)
optdepends=(
  'git-lfs: Git LFS support'
)
source=(
  "git+https://github.com/seeraven/gitcache.git#tag=v${pkgver}"
)
sha256sums=('ebf70c6bd392ef6aa17aa1635f266d65fda87385f7eeddc7e79231256e5cc686')

build() {
  cd "${srcdir}/${pkgname}"
  python -m build --wheel --no-isolation
}

package() {
  cd "${srcdir}/${pkgname}"

  python -m installer --destdir="${pkgdir}" dist/*.whl
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
