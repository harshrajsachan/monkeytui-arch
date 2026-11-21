# Maintainer: Harsh Raj Sachan
pkgname=monkeytui
pkgver=0.1.0
pkgrel=1
pkgdesc="A Monkeytype-inspired terminal typing application"
arch=('any')
url="https://github.com/harshrajsachan/MonkeyTui"
license=('MIT')
depends=('java-runtime>=17')

source=(
    "MonkeyTui.jar::https://github.com/harshrajsachan/MonkeyTui/releases/download/v${pkgver}/MonkeyTui.jar"
    "LICENSE::https://raw.githubusercontent.com/harshrajsachan/MonkeyTui/v${pkgver}/LICENSE"
)

sha256sums=('43f771d01aa330bb83d7fdae4139398e34e9771e620a2eb51611948fa3c593ba'
    '822426cfb97d2f7270ad6b640e7a4d67862c8854a8fc32ec60f0c50dff01ecd1')

package() {
    install -Dm644 "$srcdir/MonkeyTui.jar" \
        "$pkgdir/usr/share/java/monkeytui/MonkeyTui.jar"

    install -Dm755 /dev/stdin "$pkgdir/usr/bin/monkeytui" <<'EOF'
#!/bin/sh
exec /usr/bin/java -jar /usr/share/java/monkeytui/MonkeyTui.jar "$@"
EOF

    install -Dm644 "$srcdir/LICENSE" \
        "$pkgdir/usr/share/licenses/monkeytui/LICENSE"
}
