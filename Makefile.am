# Makefile.am - build XPACMAN
# Copyright (C) 2024 Jose Da Silva
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 2 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA  02111-1307  USA
#

SUBDIRS = . desktop

ACLOCAL_AMFLAGS = -I m4 ${ACLOCAL_FLAGS}

bin_PROGRAMS = xpacman
man_MANS = xpacman.6

xpacman_CPPFLAGS = ${CFLAGS}
xpacman_LDFLAGS = ${LDFLAGS}
xpacman_LDADD = -lX11 -lm
xpacman_SOURCES = xpacman.c

DISTCLEANFILES = xpacman.pc

EXTRA_DIST = xpacman.6 xpacman.jpg README.md COPYING
nodist_EXTRA_DATA = .git .github

strip:
	${STRIP} ${builddir}/xpacman
