## 
## Makefile.am 
##

AM_CFLAGS=-I$(top_srcdir)/include -I$(top_srcdir)/include/dicom
AM_LDFLAGS=

bin_PROGRAMS=mri_parse_sdcmdir
mri_parse_sdcmdir_SOURCES=mri_parse_sdcmdir.c
mri_parse_sdcmdir_LDADD=$(addprefix $(top_builddir)/, $(LIBS_MGH))
mri_parse_sdcmdir_LDFLAGS=$(OS_LDFLAGS)

# trick to get test data into build dir
foo_SOURCES=
foo:
	if ! test -f "$(top_builddir)/mri_parse_sdcmdir/98915109"; then \
		cp -v $(top_srcdir)/mri_parse_sdcmdir/98915109 \
					$(top_srcdir)/mri_parse_sdcmdir/test_dicomdir.sumfile \
					$(top_builddir)/mri_parse_sdcmdir/; fi;

check_PROGRAMS=foo

TESTS=test_mri_parse_sdcmdir

EXTRA_DIST=test_mri_parse_sdcmdir 98915109 test_dicomdir.sumfile 

# Our release target. Include files to be excluded here. They will be
# found and removed after 'make install' is run during the 'make
# release' target.
EXCLUDE_FILES=
include $(top_srcdir)/Makefile.extra
