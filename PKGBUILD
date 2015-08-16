
# Contributor: Zolotopypov Vladimir <vova7890@mail.ru>


pkgname=kdebindings-qyoto-git
pkgver=20120206
pkgrel=1
pkgdesc="New Qyoto bindings of Qt for CSharp, based on assemblygen generator. kdebindings-qyoto - is deprecated, and work not correctly."
url="http://kde.org/"
arch=('i686' 'x86_64')
license=('GPL' 'LGPL' 'FDL')
groups=('kdebindings')
depends=('kdebindings-smokeqt' 'mono')
makedepends=('cmake' 'automoc4' 'kdebindings-smokegen')
conflicts=('kdebindings-csharp' 'kdebindings-qyoto')


build() {
  cd "${srcdir}"
  git clone git://anongit.kde.org/assemblygen --depth 1
  cd "assemblygen"
  
  mkdir -p build
  cd build
  cmake ../ \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DENABLE_KIMONO_PLUGIN=FALSE
    
  make
}


package() {
  cd "assemblygen/build"
  make DESTDIR="${pkgdir}" install
}




