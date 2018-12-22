# $OpenBSD: Makefile.template,v 1.78 2018/07/09 15:00:06 jca Exp $

COMMENT =	realtime plotting utility for terminals

GH_ACCOUNT =	tenox7
GH_PROJECT =	ttyplot
GH_TAGNAME =	1.0

CATEGORIES =	sysutils

MAINTAINER =	Frederic Cambus <fcambus@openbsd.org>

# Unlicense
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB +=	c curses

NO_TEST =	Yes

do-build:
	cd ${WRKSRC} && ${CC} ${CFLAGS} ttyplot.c -o ttyplot -lcurses

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/ttyplot ${PREFIX}/bin
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/ttyplot
	${INSTALL_DATA} ${WRKSRC}/README.md ${PREFIX}/share/doc/ttyplot

.include <bsd.port.mk>
