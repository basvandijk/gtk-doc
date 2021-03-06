## Process this file with automake to produce Makefile.in
ACLOCAL_AMFLAGS=-I m4 ${ACLOCAL_FLAGS}

SUBDIRS = buildsystems/autotools buildsystems/cmake help tests

bin_SCRIPTS = \
	gtkdoc-check    \
	gtkdoc-depscan  \
	gtkdoc-fixxref  \
	gtkdoc-mkdb     \
	gtkdoc-mkhtml   \
	gtkdoc-mkhtml2  \
	gtkdoc-mkman    \
	gtkdoc-mkpdf    \
	gtkdoc-rebase   \
	gtkdoc-scan     \
	gtkdoc-scangobj

gtkdocdatadir = $(datadir)/gtk-doc/data
gtkdocdata_DATA = \
	gtk-doc.xsl		\
	version-greater-or-equal.xsl \
	devhelp2.xsd		\
	devhelp2.xsl		\
	style/home.png			\
	style/left.png			\
	style/left-insensitive.png		\
	style/right.png		\
	style/right-insensitive.png		\
	style/up.png			\
	style/up-insensitive.png		\
	style/style.css

pylibdatadir = $(datadir)/gtk-doc/python/gtkdoc
pylibdata_DATA = \
  gtkdoc/__init__.py \
  gtkdoc/check.py \
  gtkdoc/common.py \
  gtkdoc/config.py \
  gtkdoc/fixxref.py \
  gtkdoc/highlight.py \
  gtkdoc/md_to_db.py \
  gtkdoc/mkdb.py \
  gtkdoc/mkhtml.py \
  gtkdoc/mkhtml2.py \
  gtkdoc/mkman.py \
  gtkdoc/mkpdf.py \
  gtkdoc/rebase.py \
  gtkdoc/scan.py \
  gtkdoc/scangobj.py

pkgconfigdir = $(datadir)/pkgconfig
pkgconfig_DATA = gtk-doc.pc

EXTRA_DIST = \
	MAINTAINERS     \
	$(gtkdocdata_DATA) \
	$(pylibdata_DATA) \
	gtk-doc.pc.in   \
	gtk-doc.doap \
	gtk-doc-fo.xsl     \
	doc/README            \
	doc/authors.txt       \
	doc/gnome.txt         \
	doc/sections-file.txt \
	doc/setting-up.txt    \
	doc/style-guide.txt   \
	examples/README       \
	examples/Makefile.am  \
	tools/docpercentages.pl \
	tools/gtk-doc.el \
	COPYING-DOCS

CLEANFILES = \
  gtkdoc-checkc \
  gtkdoc-depscanc \
  gtkdoc-fixxrefc \
  gtkdoc-mkdbc \
  gtkdoc-mkhtmlc \
  gtkdoc-mkhtml2c \
  gtkdoc-mkmanc \
  gtkdoc-mkpdfc \
  gtkdoc-rebasec \
  gtkdoc-scangobjc \
  gtkdoc/__init__.pyc \
  gtkdoc/check.pyc \
  gtkdoc/common.pyc \
  gtkdoc/config.pyc \
  gtkdoc/fixxref.pyc \
  gtkdoc/md_to_db.pyc \
  gtkdoc/mkdb.pyc \
  gtkdoc/mkhtml.pyc \
  gtkdoc/mkhtml2.pyc \
  gtkdoc/mkman.pyc \
  gtkdoc/mkpdf.pyc \
  gtkdoc/rebase.pyc \
  gtkdoc/scan.pyc \
  gtkdoc/scangobj.pyc

DISTCLEANFILES = \
  gtkdoc-check \
  gtkdoc-depscan \
  gtkdoc-fixxref \
  gtkdocize \
  gtkdoc-mkdb \
  gtkdoc-mkhtml \
  gtkdoc-mkhtml2 \
  gtkdoc-mkman \
  gtkdoc-mkpdf \
  gtk-doc.pc \
  gtkdoc-rebase \
  gtkdoc-scangobj \
  gtkdoc-scan \
  gtkdoc/config.py

MAINTAINERCLEANFILES = \
	$(GITIGNORE_MAINTAINERCLEANFILES_TOPLEVEL) \
	$(GITIGNORE_MAINTAINERCLEANFILES_MAKEFILE_IN) \
	$(GITIGNORE_MAINTAINERCLEANFILES_M4_LIBTOOL) \
	INSTALL \
	RELNOTES.txt \
	ChangeLog-?.?? \
	gtk-doc-*.tar.xz \
	build-aux \
	__pycache__ gtkdoc/__pycache__ tests/__pycache__

-include $(top_srcdir)/git.mk

dist-hook:
	@if test -d "$(srcdir)/.git"; \
	then \
		echo Creating ChangeLog && \
		( cd "$(top_srcdir)" && \
		  echo '# Generated by Makefile. Do not edit.'; echo; \
		  $(top_srcdir)/missing --run git log --stat ) > ChangeLog.tmp \
		&& mv -f ChangeLog.tmp $(top_distdir)/ChangeLog \
		|| ( rm -f ChangeLog.tmp ; \
		  echo Failed to generate ChangeLog >&2 ); \
	else \
		echo A git clone is required to generate a ChangeLog >&2; \
	fi
