m4_define([lib_current],1)
m4_define([lib_revision],0)
m4_define([lib_age],0)

AC_INIT(cnbitk-bochum-support,[lib_current.lib_revision.lib_age],
		luca.tonin@epfl.ch)
#AC_CONFIG_SRCDIR([src/CmEngine.hpp])
AC_CONFIG_AUX_DIR([build-aux])
AC_CONFIG_MACRO_DIR([m4])
AC_CONFIG_HEADERS([config/config.h])

AM_INIT_AUTOMAKE([no-dist-gzip dist-bzip2 color-tests subdir-objects])
m4_ifdef([AM_SILENT_RULES], [AM_SILENT_RULES([yes])])

AC_CANONICAL_HOST
AC_CANONICAL_BUILD

AC_PROG_LIBTOOL
AC_PROG_CXX
AX_CXX_COMPILE_STDCXX_11
CFLAGS+=" -std=c11"
LT_INIT([win32-dll disable-static])
AC_SUBST(LIBTOOL_DEPS)

save_LIBS="$LIBS"

AC_SEARCH_LIBS_CLASS([cnbi::mobile::CmEngine], [cnbimobile], [#include <cnbimobile/CmEngine.hpp>], ,
			AC_MSG_ERROR([The cnbimobile library cannot be found.]))
LIBS="$save_LIBS"

# Python
AM_PATH_PYTHON([3])
PY_PREFIX=`python -c 'import sys ; print (sys.prefix)'`
PYTHON_LIBS="-lpython$PYTHON_VERSION"
PYTHON_CFLAGS="-I$PY_PREFIX/include/python$PYTHON_VERSION"

AC_SUBST([PYTHON_LIBS])
AC_SUBST([PYTHON_CFLAGS])
dnl Checking python3-tk
AC_MSG_CHECKING([for the python3-tk package])
ac_tk_result=`python3 -c 'try:
    from tkinter import *
except Exception, e:
    print str(e)' 2> /dev/null`

if test -z "$ac_tk_result"; then
    AC_MSG_RESULT([yes])
else
    AC_MSG_RESULT([no])
    AC_MSG_ERROR([cannot import Python module "tkinter".
    Please check if you have python3-tk installed. The error was:
    $ac_tk_result])
fi

AC_HEADER_STDBOOL

AC_SUBST([RELEASE],[lib_release])
AC_SUBST([CURRENT],[lib_current])
AC_SUBST([REVISION],[lib_revision])
AC_SUBST([AGE],[lib_age])
AC_SUBST(AM_LDFLAGS)

AC_CONFIG_FILES([Makefile])

AC_OUTPUT
