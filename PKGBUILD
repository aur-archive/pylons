#Maintainer: David Campbell <davekong@archlinux.us>
#Contributor: Cilyan Olowen <gaknar@gmail.com>
pkgname=pylons
pkgver=1.0
pkgrel=2
pkgdesc='A lightweight web framework emphasizing flexibility and rapid development.'
arch=('any')
url='http://pylonshq.com/'
license=('custom:BSD')
depends=('python2'                    'python-routes>=1.12'      'python-webhelpers>=0.6.4'
         'python-beaker>=1.3'         'python-paste>=1.7.2'      'python-paste-deploy>=1.3.3'
         'python-paste-script>=1.7.3' 'python-formencode>=1.2.1'
         'python-simplejson>=2.0.8'   'python-decorator>=2.3.2'  'python-nose>=0.10.4'
         'python-mako>=0.2.4'         'python2-webob>=0.9.6.1'   'python-weberror>=0.10.1'
         'python-webtest>=1.1'        'python2-tempita>=0.2')
makedepends=('setuptools')
source=(http://pypi.python.org/packages/source/P/Pylons/Pylons-${pkgver}.tar.gz)
replaces=('python-pylons')
md5sums=('b7687e26d0275eaf7bf44ca4883f4428')

build() {
  cd $srcdir/Pylons-${pkgver}
  python2 setup.py install --root=$pkgdir/ --optimize=1
  install -Dm644 LICENSE $pkgdir/usr/share/licenses/$pkgname/LICENSE
  sed -i -e "s|#![ ]*/usr/bin/python$|#!/usr/bin/python2|" \
         -e "s|#![ ]*/usr/bin/env python$|#!/usr/bin/env python2|" \
    $(find $pkgdir -name '*.py')
}
