pkgname=xppentab-starg960s-driver
pkgver=1
pkgrel=1
pkgdesc="Linux driver for XPPen Star G960S Tablet"
arch=('any')
url="https://github.com/ramallahos/$pkgname"
license=('LGPL')
makedepends=('coreutils')
source=("https://download01.xp-pen.com/file/2023/03/XPPen-pentablet-3.2.3.230215-1.x86_64.tar.gz" "$pkgname::git+$url.git")
sha256sums=('SKIP' 'SKIP')

build() {
#cd xp-pen-pentablet-3.2.3.230215-1.x86_64
tar -xvzf *.tar.gz
}

package() {
    cd xp-pen-pentablet-3.2.3.230215-1.x86_64
    sudo install -Dm 777 ./App/lib/udev/rules.d/10-xp-pen.rules /lib/udev/rules.d/10-xp-pen.rules
    sudo cp -rf ./App/usr/lib/pentablet /usr/lib
    sudo chmod +0755 /usr/lib/pentablet/pentablet.sh
    sudo chmod +0555 /usr/lib/pentablet/pentablet
    sudo install -Dm 777 ./App/usr/share/applications/xppentablet.desktop /usr/share/applications/xppentablet.desktop
    sudo install -Dm 777 ./App/usr/share/icons/pentablet.png /usr/share/icons/pentablet.png
    sudo install -Dm 777 ./App/etc/xdg/autostart/xppentablet.desktop /etc/xdg/autostart/xppentablet.desktop
    sudo chmod +0777 /usr/lib/pentablet/pentablet
    sudo chmod +0777 /usr/lib/pentablet/pentablet.sh
    sudo chmod +0666 /usr/lib/pentablet/resource.rcc
    sudo chmod +0777 /usr/lib/pentablet/conf/xppen
    sudo chmod +0777 /usr/lib/pentablet/lib
    sudo chmod +0777 /usr/lib/pentablet/platforms
    sudo chmod +0666 /usr/lib/pentablet/conf/xppen/*
    sudo chmod +0666 /usr/lib/pentablet/conf/xppen/*
    cd ../"$pkgname"
    sudo rm -f /usr/lib/pentablet/conf/xppen/language.ini
    sudo rm -f /usr/lib/pentablet/conf/xppen/config.xml
    sudo install -Dm 644 language.ini /usr/lib/pentablet/conf/xppen/language.ini
    sudo install -Dm 644 new.pcfg /usr/lib/pentablet/conf/xppen/config.xml
}
