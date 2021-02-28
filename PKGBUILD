# Maintainer :
_pkgname_dl=shadowsocks
_pkgname=shadowsocks-rust
pkgname=shadowsocks-rust-bin
pkgver=v1.9.1
pkgrel=1
pkgdesc='A Rust port of shadowsocks https://shadowsocks.org/'
arch=('x86_64')
url='https://github.com/shadowsocks/shadowsocks-rust'
license=('MIT')
depends=('openssl')
#makedepends=()
conflicts=(shadowsocks-rust)
source=(
    "${_pkgname}-${pkgver}.tar.xz::${url}/releases/download/${pkgver}/${_pkgname_dl}-${pkgver}.${arch}-unknown-linux-gnu.tar.xz"
  'shadowsocks-rust@.service'
  'shadowsocks-rust-server@.service'
  'shadowsocks-rust-manager@.service'
  'sysusers'
  'config.json'
  'config_ext.json'
)
sha512sums=('3b852a3bb01e026e3ae33e23840fb9829eca84dd25b44aded1d9bd622b7f25828094955b6173cdfe0b2ece04b60a1988a6dac5188e65ca99c4b8d00420494dba'
            '430503b00615b6b441179f76dfa3cf267d1b3a5af8ddd502a2f25bb1000bcf4a2565334baa3d37396b806b920579a01f36736e529b30c7176d909d0ed3079f00'
            'a745c520e8f75e02ef9c455be8c80c449bd5b0b83b3f99d3782ac73db0ebfaa44bb98cd1d5707a6e06776244d024a16d43ad5965d413afc847205e13b3e8c467'
            'b1d2543e99fc6450e84cdfb487e4aacc4acc72a681d9e72d5d3772023df18aab7dac36826e45b1ad21288f8839a857f55f4a53dcefe952d97a74d47f27ea1650'
            '2f9ad26dde4ba8ae069faa96158d880adad300306848a575e612183bbada1b4198840420e91bc20ba02c27adb07defe2843f1790e4e5ed0a9a41db7d6aa927e3'
            'SKIP'
            'SKIP')
package() {
  cd "${srcdir}/"
  install -Dm755 "sslocal" "${pkgdir}/usr/bin/sslocal-rust"
  install -Dm755 "ssserver" "${pkgdir}/usr/bin/ssserver-rust"
  install -Dm755 "ssurl" "${pkgdir}/usr/bin/ssurl-rust"
  install -Dm755 "ssmanager" "${pkgdir}/usr/bin/ssmanager-rust"
  install -Dm644 "shadowsocks-rust@.service" "${pkgdir}/usr/lib/systemd/system/shadowsocks-rust@.service"
  install -Dm644 "shadowsocks-rust-server@.service" "${pkgdir}/usr/lib/systemd/system/shadowsocks-rust-server@.service"
  install -Dm644 "shadowsocks-rust-manager@.service" "${pkgdir}/usr/lib/systemd/system/shadowsocks-rust-manager@.service"
  install -Dm644 "sysusers" "$pkgdir"/usr/lib/sysusers.d/$pkgname.conf
  install -Dm644 "config_ext.json" "${pkgdir}/etc/shadowsocks/config_ext_rust.json.example"
  install -Dm644 "config.json" "${pkgdir}/etc/shadowsocks/config_rust.json.example"
}

