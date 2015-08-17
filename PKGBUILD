# Contributor: Guten <ywzhaifei@gmail.com>

pkgname=rutorrent-plugin-autodl-irssi-svn
pkgver=686 
pkgrel=1
pkgdesc="autodl-irssi rutorrent plugin. see https://wiki.archlinux.org/index.php/Autodl-irssi for Installation."
arch=("i686" "x86_64")
url="http://sourceforge.net/projects/autodl-irssi/"
license=("unknown")
groups=()
depends=("rutorrent" "autodl-irssi-svn")
makedepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=("srv/http/rutorrent/plugins/autodl-irssi/conf.php")
options=()
install=
changelog=
source=()
md5sums=()

_svntrunk="https://autodl-irssi.svn.sourceforge.net/svnroot/autodl-irssi/trunk/rutorrent/autodl-irssi"
_svnmod="autodl-irssi-svn"

build() {
  cd $startdir/src

  msg "Connecting to SVN server...."
  if [ -d $_svnmod/.svn ]; then
    (cd $_svnmod && svn up -r $pkgver)
  else
    svn co $_svntrunk --config-dir ./ -r $pkgver $_svnmod
  fi
  msg "SVN checkout done or server timeout"
}

package() {
  p_plugins="${pkgdir}/srv/http/rutorrent/plugins"
  cd $srcdir/$_svnmod

  mkdir -p $p_plugins/autodl-irssi
  cp -r * $p_plugins/autodl-irssi

  cd $p_plugins/autodl-irssi
  mv _conf.php conf.php
}

# vim:set ts=2 sw=2 et:
