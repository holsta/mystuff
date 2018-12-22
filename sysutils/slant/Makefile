# $OpenBSD: Makefile,v 1.8 2017/07/25 06:44:45 bentley Exp $

COMMENT =	minimal remote system monitor

DISTNAME =	slant-0.0.13

CATEGORIES =	sysutils

HOMEPAGE =	https://kristaps.bsd.lv/slant/

MAINTAINER =	Kristaps Dzonsons <kristaps@bsd.lv>

# ISC
PERMIT_PACKAGE_CDROM =	Yes

# uses pledge()
WANTLIB += c

BUILD_DEPENDS =	www/kwebapp>=0.6.3 \
		www/kcgi \
		databases/ksql

MASTER_SITES =	https://kristaps.bsd.lv/slant/snapshots/

MAKE_ENV += 	CPPFLAGS="${CPPFLAGS} -I${LOCALBASE}/include" \
		LDFLAGS="${LDFLAGS} -L${LOCALBASE}/lib"

NO_TEST =	Yes

.include <bsd.port.mk>
