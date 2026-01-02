# Maintainer: snogard <snogardb at gmail dot com>
# Contributor: Dct Mei <dctxmei@yandex.com>
pkgbase=grub-themes-git
_pkgbase=grub2-themes
pkgname=('grub-theme-tela')
pkgver=2025.07.23.r4.g80dd04d
pkgrel=1
pkgdesc="Flat Design themes for Grub"
arch=('any')
url="https://github.com/vinceliuice/grub2-themes"
license=('GPL3')
depends=('grub')
makedepends=('git')
source=("git+${url}.git")
sha256sums=('SKIP')

pkgver() {
    cd grub2-themes
    git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

package() {
    cd grub2-themes
    
    # Run the install script to a temporary location
    ./install.sh -t tela -g "${srcdir}/temp"
    
    # Move the generated theme to the package directory
    install -dm755 "${pkgdir}/boot/grub/themes"
    cp -r "${srcdir}/temp/tela" "${pkgdir}/boot/grub/themes/"
    
    # Install license
    install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
