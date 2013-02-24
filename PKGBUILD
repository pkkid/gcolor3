pkgname=gcolor3-git
pkgbase=gcolor3
pkgver=20130224
pkgrel=1
pkgdesc="A simple color selection dialog in GTK3"
arch=(any)
url="https://github.com/Unia/gcolor3"
license=(GPL)
depends=('gtk3')

_gitroot="https://github.com/Unia/$pkgbase"
_gitname="$pkgbase"

build() {
  cd "$srcdir"
  msg "Connecting to GIT server..."

  if [ -d ${_gitname} ] ; then
    cd ${_gitname}
    git pull
    msg "The local files are updated."
  else
    git clone ${_gitroot} ${_gitname}
  fi
  msg "GIT checkout done or server timeout"
}

package() {
  cd "$srcdir/$pkgbase"
  make
  make DESTDIR="$pkgdir" install
}
md5sums=()