#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.
AC_PREREQ([2.69])

m4_define([ver_major], [1])
m4_define([ver_minor], [0])
m4_define([ver_release], [1])
# Set build number to commit count only if ".git" folder is present
m4_define([ver_build], m4_if(m4_esyscmd_s([ls -1 -d ".git" 2>&1]),.git,[m4_esyscmd_s([git rev-list --count HEAD])],[0]))

m4_define([syndwarsfx_levels_version],
      [ver_major.ver_minor.ver_release.ver_build])

AC_INIT([SyndWarsFX Levels], [syndwarsfx_levels_version], [listom@gmail.com], [syndwarsfx_levels])

m4_define([parent_package], [syndwarsfx])
AC_DEFINE([PARENT_PACKAGE], [parent_package], [Name of the parent package, for which this one provides data files])

AC_CONFIG_SRCDIR([LEVELS/C001L001.D1])
# We use header file as means to transfer properties to automation scripts
AC_CONFIG_HEADERS([levels_config.h])
AC_CONFIG_MACRO_DIRS([m4])

AC_CANONICAL_HOST
AC_CANONICAL_TARGET

AM_INIT_AUTOMAKE([foreign])
ifdef([AM_SILENT_RULES], [AM_SILENT_RULES([yes])])

# Checks for programs
PKG_PROG_PKG_CONFIG

# Default install dir
#AC_PREFIX_DEFAULT(/usr/local)

# Flags
AC_SUBST([PARENT_PACKAGE], [parent_package])

# Prepare makefiles from `.in` templates
AC_CONFIG_FILES([Makefile])

# Done - generate and execute `config.status`
AC_OUTPUT
