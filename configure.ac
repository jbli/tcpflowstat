#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ(2.59)
AC_INIT(tcpflowstat, 0.1.0, wangbin579@gmail.com)
AC_CONFIG_SRCDIR([src/stat/main.c])
AC_CONFIG_HEADER([src/core/config.h])


AM_INIT_AUTOMAKE(tcpflowstat,0.1.0)


# Checks for programs.
AC_PROG_LN_S
AC_PROG_MAKE_SET

# Checks for libraries.

AC_PROG_LIBTOOL
AM_PROG_LIBTOOL

AC_ARG_ENABLE(debug, AS_HELP_STRING([--enable-debug],[compile tcpcopy with debug support(saved in a log file)]),,debug=no)
if test "x$enable_debug" = "xyes";then
	AC_DEFINE(TCPCOPY_DEBUG, 1, [Define if --enable-debug])
fi


# Checks for header files.
AC_HEADER_STDC
AC_CHECK_HEADERS([arpa/inet.h fcntl.h limits.h netinet/in.h stdint.h stdlib.h string.h sys/file.h sys/param.h sys/socket.h sys/time.h unistd.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_HEADER_STDBOOL
AC_C_CONST
AC_C_INLINE
AC_TYPE_PID_T
AC_TYPE_SIZE_T
AC_HEADER_TIME
AC_C_VOLATILE
AC_CHECK_TYPES([ptrdiff_t])

# Checks for library functions.
AC_FUNC_MALLOC
AC_FUNC_MEMCMP
AC_FUNC_SELECT_ARGTYPES
AC_TYPE_SIGNAL
AC_FUNC_VPRINTF
AC_CHECK_FUNCS([atexit gettimeofday inet_ntoa memset select socket localtime_r])

LIBS="-lpcap"

CFLAGS="-g -Wall -Wunused-function -pedantic -I../core -I../stat -I../util"

#AC_CONFIG_FILES([Makefile])
AC_OUTPUT([
Makefile
src/Makefile
src/core/Makefile
src/util/Makefile
src/stat/Makefile
])

