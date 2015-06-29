#
# Copyright (c) 2015 Thorsten Kukuk, Germany
#
# Author: Thorsten Kukuk <kukuk@thkukuk.de>
#
# Process this file with automake to produce Makefile.in.
#

CLEANFILES = *~

EXTRA_DIST = libnss_compat.map files-parse.c

AM_CFLAGS = -D_REENTRANT=1 -D_GNU_SOURCE=1
AM_CPPFLAGS = -I$(srcdir) @LIBNSL_CFLAGS@

lib_LTLIBRARIES = libnss_compat.la

noinst_HEADERS = libc-lock.h netgroup.h nsswitch.h
noinst_PROGRAMS = nss_loader-test
nss_loader_test_LDADD = -ldl

libnss_compat_la_LDFLAGS = -version-info 2:0:0 \
	-Wl,--version-script=$(srcdir)/libnss_compat.map
libnss_compat_la_LIBADD = @LIBNSL_LIBS@
libnss_compat_la_SOURCES = compat-grp.c compat-initgroups.c compat-pwd.c \
	compat-spwd.c
