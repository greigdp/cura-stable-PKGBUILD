# Inspired by PKGBUILD from megasync on AUR
pkgname=cura-stable
_pkgname=cura
pkgver=15.04.3
pkgrel=1
pkgdesc="A full software solution for 3D printing aimed at RepRaps and the Ultimaker. This package contains both the binary Cura engine and the python front-end."
arch=('i686' 'x86_64')
url="https://ultimaker.com/en/products/cura-software"
license=('GPL3')
conflicts=('cura')
provides=('cura')
#depends=('python>=3.4' 'python-pyqt5' 'qt5-quickcontrols' 'python-pyserial' 'wxpython' 'python-numpy' 'python-opengl' 'protobuf3' 'python-protobuf3')
depends=('python2' 'wxpython' 'python2-opengl' 'python2-pyserial' 'python2-numpy')
source_i686=("http://software.ultimaker.com/current/${_pkgname}_${pkgver}-debian_i386.deb")
source_x86_64=("http://software.ultimaker.com/current/${_pkgname}_${pkgver}-debian_amd64.deb")

sha1sums_i686=('5583fd2bbf8262b26e81aa8cc6b9fa42ba0a0153')
sha1sums_x86_64=('a5313a02bb404b729c4553be8c2c08245ab7f5a0')

package (){
	cd "${srcdir}"
	pwd
	tar -xvf data.tar.xz -C ${pkgdir}/
	# Cura needs to use python2 for its launchers and scripts - Arch uses python3 as the default
	sed -i 's/\/usr\/bin\/python/\/usr\/bin\/python2/g' ${pkgdir}/usr/bin/cura
	sed -i 's/\/usr\/bin\/python/\/usr\/bin\/python2/g' ${pkgdir}/usr/share/cura/Cura/cura.py
	sed -i 's/\/usr\/bin\/env python/\/usr\/bin\/python2/g' ${pkgdir}/usr/share/cura/Cura/util/pymclevel/mce.py
	sed -i 's/\/usr\/bin\/python/\/usr\/bin\/python2/g' ${pkgdir}/usr/share/cura/cura.py
	sed -i 's/\/usr\/bin\/python/\/usr\/bin\/python2/g' ${pkgdir}/usr/share/applications/cura.desktop
}

