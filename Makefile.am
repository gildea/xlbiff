bin_PROGRAMS = xlbiff
xlbiff_SOURCES = xlbiff.c

xmhformdir = @xmhformdir@
dist_xmhform_DATA = xlbiff.form

appdefaultdir = @appdefaultdir@
appdefault_DATA = XLbiff
CLEANFILES = $(appdefault_DATA)
%: %.ad
	cp -- "$<" "$@"

# "configure" normally sets appdefaultdir for each system with "pkg-config",
# which returns an absolute pathname.  "make distcheck" doesn't use DESTDIR
# doing its test "make install", so it needs some value relative to a
# Makefile variable, so that it doesn't install into the real directory.
DISTCHECK_CONFIGURE_FLAGS = --with-appdefaultdir=\$${datadir}/X11/app-defaults

dist_man1_MANS = xlbiff.man

EXTRA_DIST = README.bulk XLbiff.ad Bcheck Bscan

# aid for building Debian source package
debian-orig-dist: dist
	mv xlbiff-$(VERSION).tar.gz ../xlbiff_$(VERSION).orig.tar.gz
.PHONY: debian-orig-dist
