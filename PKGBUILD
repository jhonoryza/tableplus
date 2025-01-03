pkgname=tableplus
pkgver=1.2.2
pkgrel=1
arch=('x86_64')
url="https://tableplus.com/"
license=('custom')
depends=('rpm-tools')
source=("https://yum.tableplus.com/rpm/x86_64/tableplus-1.2.2-258.x86_64.rpm")
sha256sums=('SKIP')  # Menggunakan SKIP karena kita mengekstrak file tanpa checksum

package() {
    # Direktori sementara untuk ekstraksi
    local tempdir="$srcdir/temp_tableplus"
    mkdir -p "$tempdir"

    # Ekstrak RPM menggunakan rpm2cpio ke direktori sementara
    rpm2cpio "${srcdir}/tableplus-1.2.2-258.x86_64.rpm" | cpio -idmv -D "$tempdir"

    # Pastikan direktori tujuan ada sebelum menyalin file
    mkdir -p "$pkgdir/opt/tableplus"
    mkdir -p "$pkgdir/usr/lib/.build-id/cf"

    # Pindahkan file ke direktori tujuan
    mv "$tempdir/opt/tableplus" "$pkgdir/opt/"
    mv "$tempdir/usr/lib/.build-id/cf" "$pkgdir/usr/lib/.build-id/cf"
}

