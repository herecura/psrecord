# Maintainer: graysky <graysky AT archlinux DOT us>
pkgname=psrecord
pkgver=1.2
pkgrel=1
pkgdesc="Record and plot the CPU and memory activity of a process."
arch=('any')
url="https://github.com/astrofrog/psrecord"
license=('BSD')
depends=('python-psutil')
checkdepends=('python-matplotlib')
makedepends=('python-pytest')
optdepends=('python-matplotlib: to generate plots of the data')
source=("$pkgname-$pkgver.tar.gz::https://github.com/astrofrog/psrecord/archive/v$pkgver.tar.gz")
sha256sums=('f08d5461eefbd7693f1481faa797f9a45396185bc69a833fad00d241cb3ff355')

build() {
  cd "$pkgname-$pkgver"
  python setup.py build
}

check() {
  cd "$pkgname-$pkgver"
  pytest psrecord
}

package() {
  cd "$pkgname-$pkgver"
  python setup.py install --root="$pkgdir" --optimize=1
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
