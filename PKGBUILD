pkgname=cadaver
pkgver=0.23.3
pkgrel=2
pkgdesc='Command-line WebDAV client for Unix'
arch=('x86_64')
url='http://www.webdav.org/cadaver'
license=('GPL')
depends=('neon')
source=(http://www.webdav.org/cadaver/cadaver-${pkgver}.tar.gz
        disable-sslv2.patch)
md5sums=('502ecd601e467f8b16056d2acca39a6f'
         'cbcf9db91efe751c523d6835d2abee43')

prepare() {
  cd ${srcdir}/cadaver-${pkgver}
  patch -p1 -i ${srcdir}/disable-sslv2.patch
}

build() {
  cd ${srcdir}/cadaver-${pkgver}
  ./configure --prefix=/usr --with-ssl
  make
}

package() {
  cd ${srcdir}/cadaver-${pkgver}
  make prefix=${pkgdir}/usr install
}
