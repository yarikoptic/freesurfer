##
## Makefile.am 
##

#######################################################################
# When you create your own program directory, copy the 'from' to the 
# 'to' lines to your Makefile.am and change dummy to your program name.
#  
# 0. mkdir  dev/yourdir and put .c file in there
# 1. modify dev/configure.in to have yourdir/Makefile
# 2. modify dev/Makefile.am to have yourdir as one of SUBDIRS
# 3. create dev/yourdir/Makefile.am  (follow dummy/Makefile.am)
#      i.e. replace dummy with your program name.
#
# 4. ./setup_configure at the top directory, i.e. dev/ (which will create 
#    Makefile.in in yourdir directory and configure from configure.in)
# 5. ./configure .... and make to make sure that your new thing is working
# 6. try make to make sure that yourthing is compiled.
#
# After confirming everything working:
# 7. checkin yourdir/Makefile.am, yourdir/yourprog.c or cpp.  
#    (Don't checkin Makefile or Makefile.in.)
# 8. commit dev/configure.in, dev/Makefile.am
#
# 9. lastly, delete this help text from your own Makefile.am!
#
# If you have problems, please let us know (zkaufman@nmr.mgh.harvard.edu
# or nicks@nmr.mgh.harvard.edu).
#########################################################################
# from ------------------------------------------------

AM_CFLAGS=-I$(top_srcdir)/include
AM_CXXFLAGS=-I$(top_srcdir)/include

bin_PROGRAMS = mri_fdr
mri_fdr_SOURCES=mri_fdr.c
mri_fdr_LDADD= $(addprefix $(top_builddir)/, $(LIBS_MGH))
mri_fdr_LDFLAGS=$(OS_LDFLAGS)

# to --------------------------------------------------
#
# Where $(OS_LDFLAGS) is to compile programs statically for Linux.
#
# You can have multiple bin_PROGRAMS in the same directory.
#
########################################################################
# When you want to create your program to test, use the following 
# framework:
# You can have as many programs (separated by space) in check_PROGRAMS.
# Your program can consist of many sources (you add to _SOURCES= line).
# You can do "make myown" to compile. The default CFLAGS="-g -O2", but
# you can do "make CFLAGS=-g myown" to create a debugging version.
#
# The program listed as check_PROGRAMS are not compiled under standard 
# "make". Only "make check" will compile them. See mri_convert's
# Makefile.am for an example of its 'make check' test setup.
# 

# Our release target. Include files to be excluded here. They will be
# found and removed after 'make install' is run during the 'make
# release' target.
EXCLUDE_FILES=
include $(top_srcdir)/Makefile.extra
