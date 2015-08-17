# Maintainer: Limao Luo <luolimao+AUR@gmail.com>

pkgname=topographica
pkgver=0.9.8
pkgrel=1
pkgdesc="A general-purpose neural simulator focusing on topographic maps, large scale networks like brain"
arch=(any)
url=http://topographica.org/
license=(BSD)
depends=(python2-gmpy python2-imaging python2-matplotlib python2-numpy python2-scipy)
source=($pkgname.tar.gz::https://sourceforge.net/projects/$pkgname/files/$pkgname/$pkgver/$pkgname-$pkgver.tar.gz/download)
sha256sums=('091acefcf03633f7db658ccdb0f1c253b3cffb882f906c3b6434ef1a15489587')
sha512sums=('c8dfc5effc7acac33376ddfe1ee23541d14d7bdc3be1a63a26e1269ccc6f88c34e19ccc1738fe6b2e498719f880cb5231b3c303f18639adb44c381bf1fd9ac95')

prepare() {
    sed -ri 's:^#!/usr/bin/(env )?python$:&2:' $pkgname-$pkgver/topo/misc/asizeof.py
}

build() {
    cd $pkgname-$pkgver/
    python2 setup.py build
}

package() {
    cd $pkgname-$pkgver/
    python2 setup.py install --root="$pkgdir" --optimize=1
    install -Dm644 LICENSE.txt "$pkgdir"/usr/share/licenses/$pkgname/LICENSE
}
