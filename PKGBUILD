pkgname=packer
pkgver=20100904
pkgrel=1
pkgdesc="Bash wrapper for pacman and aur"
url="http://github.com/bruenig/packer"
license="GPL"
arch=('any')
makedepends=('git')
depends=('grep' 'sed' 'coreutils' 'bash' 'wget' 'pacman')
optdepends=('sudo: install and update packages as non-root'
            'pacman-color: colorized output')
_gitroot='git://github.com/cdkamat/packer.git'
_gitname='packer'

build() {
  cd ${srcdir}
  msg "Connecting to GIT server...."
  if [ -d "${srcdir}/${_gitname}" ] ; then
    cd ${_gitname} && git checkout master && git pull
  else
    git clone ${_gitroot}
  fi

  msg "GIT checkout done"
  msg "Starting make..."
  
  install -m 755 -D $srcdir/$_gitname/packer "$startdir/pkg/usr/bin/packer"
  install -m 644 -D $srcdir/$_gitname/packer.8 "$startdir/pkg/usr/share/man/man8/packer.8"
}

