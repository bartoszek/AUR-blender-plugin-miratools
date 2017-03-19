# Maintainer: bartus <szczepaniak.bartek+aur@gmail.com>
# original maintainer : Fabien Devaux <fdev31@gmail.com>

pkgname=blender-plugin-miratools
pkgver=r569.87031bc # commit-num.commit-hash 
pkgrel=2
pkgdesc="Modern modeling and retopology tools"
url="https://github.com/mifth/mifthtools/wiki/Mira-Tools"
license=("GPL")
arch=('any')
depends=('blender')
groups=('blender')
makedepends=('git')
source=("${pkgname}::git+https://github.com/mifth/mifthtools.git")
md5sums=('SKIP')

pkgver() {
  cd ${pkgname}
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
    addons="$pkgdir/usr/share/blender/$(blender -v | head -n1 | cut -f2 -d ' ')/scripts/addons/"
  install -d 755 ${addons}/${name}
  cp -a ${srcdir}/${pkgname}/blender/addons/* ${addons}/${name}
#  cp -r "$srcdir/mifthtools-$_h/blender/addons/"* "$addons"
}

