AC_INIT(sgte, 0.7, pacini@sgconsulting.it, sgte)
AC_PREREQ(2.59c)
AC_COPYRIGHT(Copyright (C) 2006-2008 S.G. Consulting)

EBLOG_DIR=$(dirname `pwd`)
AC_SUBST(EBLOG_DIR)

AC_ERLANG_NEED_ERL
AC_ERLANG_NEED_ERLC

AC_ERLANG_SUBST_ROOT_DIR

dnl C support

AC_PROG_CC

case "$target_os" in
     *cygwin*)
        :
        dnl fix this later
        ;;
      linux*)
        AC_DEFINE(LINUX,,LINUX)
        LD_SHARED="ld -shared"
        ;;
      *bsd*)
        AC_DEFINE(BSD,,BSD)
        LD_SHARED="ld -Bshareable"
        ;;
      *solaris*)
        AC_DEFINE(SOLARIS,,SOLARIS)
        LD_SHARED="ld -G"
        ;;
      *darwin*)
        AC_DEFINE([DARWIN], [], [Description])
        LD_SHARED="cc -bundle -flat_namespace -undefined suppress"
        ;;
      *)
        LD_SHARED="ld -shared"
        ;;
esac

AC_SUBST(LD_SHARED)


define(OUTPUT_FILES,
	include.mk)

AC_OUTPUT(OUTPUT_FILES,
[
])dnl
