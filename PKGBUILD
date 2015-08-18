# Contributor: Denis Terskov aka neurosurgeon <terskov.den@gmail.com>
pkgname=xneur-subversion
pkgver=623
pkgrel=1
pkgdesc="X neural layout switcher - it detects the language of input and corrects it if needed (svn-version)"
url="http://xneur.ru/"
arch=(i686 x86_64)
license="GPL"
depends=('gstreamer0.10' 'aspell' 'xosd' 'libmatheval')
makedepends=('subversion')
optdepends=('gxneur-subversion: GTK+ frontend for xneur')
source=()
md5sums=()

_svntrunk=svn://xneur.ru:3690/xneur/xneur
_svnmod=xneur

build() {
	cd $startdir/src/    
	msg "Connecting to Xneur SVN server...."
	svn co $_svntrunk $_svnmod 

	msg "SVN checkout done or server timeout"
  	msg "Starting make..."

	cd $startdir/src/$_svnmod
	./autogen.sh --prefix=/usr
	make || return 1
   	make DESTDIR=$startdir/pkg install
}
