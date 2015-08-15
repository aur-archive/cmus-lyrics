# Maintainer: OK100 <ok100.ok100.ok100@gmail.com>

pkgname=cmus-lyrics
pkgver=20120625
pkgrel=1
pkgdesc="A simple lyrics viewer for cmus, shell-fm, pianobar, mpd and moc"
url="https://github.com/ok100/cmus-lyrics"
arch=(any)
license=('WTFPLv2')
install=cmus-lyrics.install
depends=('python' 'glyr-git')
optdepends=('cmus: cmus support'
            'shell-fm: shell-fm support'
            'pianobar: pianobar support'
            'mpd: mpd support'
            'mpc: mpd support'
            'moc: moc support')
makedepends=('git')

_gitroot="git://github.com/ok100/cmus-lyrics.git"
_gitname="cmus-lyrics"

build() {
  cd "$srcdir"
  msg "Connecting to GIT server..."

  if [ -d $_gitname ] ; then
    cd $_gitname && git pull origin
    msg "The local files are updated."
  else
    git clone $_gitroot $_gitname
  fi
  msg "GIT checkout done or server timeout"
}

package() {
  cd "$srcdir/$_gitname"
  install -m755 -D $pkgname $pkgdir/usr/bin/$pkgname
}

# vim:set ts=2 sw=2 et:
