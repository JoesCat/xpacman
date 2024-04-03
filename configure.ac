#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

# Copyright (C) 2024 by Joe Da Silva

AC_PREREQ([2.70])

m4_define([xpacman_version], [0.11])
AC_INIT([xpacman],[xpacman_version],[https://github.com/JoesCat/xpacman/issues],
	[xpacman],[https://github.com/JoesCat/xpacman])
AC_CONFIG_SRCDIR([xpacman.c])
AC_CANONICAL_TARGET
AC_CANONICAL_HOST
AC_CANONICAL_BUILD
AM_INIT_AUTOMAKE([foreign -Wall])
AC_USE_SYSTEM_EXTENSIONS
AC_SUBST([XPACMAN_VERSION],[xpacman_version])
AC_CHECK_TOOL([STRIP],[strip],[:])
AC_PROG_CC
AC_PROG_RANLIB
AC_PROG_INSTALL
AC_PROG_MKDIR_P
AC_PROG_MAKE_SET

#-------------------------------------------
# Enable silent build rules by default, this
# requires atleast Automake-1.11. Disable by
# either passing --disable-silent-rules to
# configure or passing V=1 to make
m4_ifdef([AM_SILENT_RULES],[AM_SILENT_RULES([yes])],[AC_SUBST([AM_DEFAULT_VERBOSITY],[1])])

#-------------------------------------------
# Check for math.h include and math library.
have_libm=no
AC_CHECK_HEADER([math.h],
  AC_SEARCH_LIBS([cos],[m],[have_libm=yes],))
if test x"${have_libm}" != xyes; then
   AC_MSG_FAILURE([ERROR: Please install Math libraries and math.h include files for libm],[1])
fi

#-------------------------------------------
# Required development include files (and associated libraries)
AC_MSG_CHECKING([Check for X11 and required developer header files])
AC_CHECK_HEADER([X11/Xlib.h],[],[AC_MSG_FAILURE([ERROR: Missing X11/Xlib.h, Please install Developer version of libx11-devel or lib64x11-devel],[1])])

#-------------------------------------------
AC_CONFIG_FILES([Makefile desktop/Makefile])
AC_OUTPUT
AC_MSG_NOTICE([

Configuration:

  Source code location	${srcdir}
  Build code location	${builddir}
  Destination prefix	${prefix}
  Host Operating System	${host}
  Compiler		${CC}
  Config CFLAGS		"${CFLAGS}"
  Config LDFLAGS	"${LDFLAGS}"

])
