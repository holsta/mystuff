# $OpenBSD: Makefile,v 1.29 2017/11/16 23:20:39 naddy Exp $

COMMENT =	command line time tracker

VERSION =	1.1.1
DISTNAME =	timew-${VERSION}
PKGNAME =	timewarrior-${VERSION}
CATEGORIES =	productivity
REVISION =	3

HOMEPAGE =	http://www.taskwarrior.org/

MASTER_SITES =	${HOMEPAGE}download/

# MIT
PERMIT_PACKAGE_CDROM =		Yes

# Needs C++11; linker issues with clang
COMPILER =		base-clang ports-gcc
MODULES =		devel/cmake \
			lang/lua \
			lang/python
MODLUA_SA =		Yes

WANTLIB += c gnutls m pthread ${COMPILER_LIBCXX}

LIB_DEPENDS =		security/gnutls

CONFIGURE_STYLE =	cmake

CONFIGURE_ARGS +=	-DTASK_DOCDIR=share/taskwarrior \
			-DTASK_MAN1DIR=man/man1 \
			-DTASK_MAN5DIR=man/man5

CONFIGURE_ENV +=	CFLAGS="-I${LOCALBASE}/include" \
			LDFLAGS="-L${LOCALBASE}/lib"

NO_TEST =		Yes

#pre-configure:
#	@sed -i 's,share/doc/timew/,share/timewarrior/,g' \
#		${WRKSRC}/doc/man/task-color.5.in \
#		${WRKSRC}/doc/man/taskrc.5.in \
#		${WRKSRC}/src/Config.cpp
#	@sed -i 's,share/doc/task-VERSION/,share/timewarrior/,g' \
#		${WRKSRC}/scripts/vim/README

#post-install:
#	${MODPY_BIN} ${MODPY_LIBDIR}/compileall.py \
#	    ${PREFIX}/share/timewarrior/scripts/add-ons

.include <bsd.port.mk>
