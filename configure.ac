AC_PREREQ(2.52)

m4_define([required_apertium_version], [3.1.0])

AC_INIT([apertium-en-ca], [0.8.9], [mginesti@dlsi.ua.es])
AM_INIT_AUTOMAKE([apertium-en-ca], [0.8.9], no-define)
AC_PROG_LN_S
AC_PROG_AWK
AC_CONFIG_HEADER([config])


PKG_CHECK_MODULES(APERTIUM,   apertium >= required_apertium_version, [], [PKG_CHECK_MODULES(APERTIUM,   apertium-3.2 >= required_apertium_version)])


AC_PATH_PROG(XSLTPROC, xsltproc, no)
if test x$ac_cv_path_XSLTPROC = x
then
  AC_MSG_ERROR([You don't have xsltproc installed.])
fi
if test x$ac_cv_path_XSLTPROC = xno
then
  AC_MSG_ERROR([You don't have xsltproc installed.])
fi

PKG_CHECK_MODULES(REGTEST, apertium-regtest >= 0.0.1, [],
                  [AC_MSG_WARN([Running tests requires apertium-regtest])])

AP_MKINCLUDE

AC_OUTPUT([Makefile])
