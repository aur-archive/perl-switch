# CPAN Name  : Switch
# Contributor: AUR Perl <aurperl@juster.info>
# Generator  : CPANPLUS::Dist::Arch 1.12

pkgname='perl-switch'
pkgver='2.16'
pkgrel='1'
pkgdesc="A switch statement for Perl"
arch=('any')
license=('PerlArtistic' 'GPL')
options=('!emptydirs')
depends=('perl')
makedepends=()
url='http://search.cpan.org/dist/Switch'
source=('http://search.cpan.org/CPAN/authors/id/R/RG/RGARCIA/Switch-2.16.tar.gz' 'switch.diff')
md5sums=('bf75dc7f171b4718a2118c3d6cbe6013'
    'd4d48e5ef390f807d1f929ddc0808b4a')
_distdir="${srcdir}/Switch-2.16"

build() {
  ( export PERL_MM_USE_DEFAULT=1 PERL5LIB=""                 \
      PERL_AUTOINSTALL=--skipdeps                            \
      PERL_MM_OPT="INSTALLDIRS=vendor DESTDIR='$pkgdir'"     \
      PERL_MB_OPT="--installdirs vendor --destdir '$pkgdir'" \
      MODULEBUILDRC=/dev/null

    cd "$_distdir"
    patch -p1 < "$srcdir/switch.diff"
    /usr/bin/perl Makefile.PL
    make
  )
}

check() {
  cd "$_distdir"
  ( export PERL_MM_USE_DEFAULT=1 PERL5LIB=""
    make test
  )
}

package() {
  cd "$_distdir"
  make install
  find "$pkgdir" -name .packlist -o -name perllocal.pod -delete
}

# Local Variables:
# mode: shell-script
# sh-basic-offset: 2
# End:
# vim:set ts=2 sw=2 et:
