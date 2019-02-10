# $OpenBSD: Makefile,v 1.24 2019/02/07 15:50:09 edd Exp $

COMMENT =	open decentralized synchronization utility

V =		0.8.0-preview
DISTNAME =	bosun-${V}
DISTFILES =	${V}${EXTRACT_SUFX}

CATEGORIES =	sysutils
HOMEPAGE =	https://bosun.org/

MAINTAINER =	Alex Holst <a@mongers.org>

# MPL 2.0
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += c pthread

MASTER_SITES = https://github.com/bosun-monitor/bosun/archive/

WRKDIST =		${WRKDIR}/bosun-${V}
WRKSRC =		${WRKDIR}/go/src/github.com/bosun-monitor/bosun
SUBST_VARS +=		VARBASE

MODULES =		lang/go
MODGO_TYPE =		bin
MODGO_ENV =		PATH="${PORTPATH}" HOME="${PORTHOME}"

do-build:
	cd ${WRKSRC}/cmd/bosun && ${MODGO_CMD} build
	cd ${WRKSRC}/cmd/scollector && ${MODGO_CMD} build
	cd ${WRKSRC}/cmd/silence && ${MODGO_CMD} build

do-test:
	cd ${WRKSRC}/build && ${MODGO_CMD} run build.go test

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/bin/bosun ${PREFIX}/bin/
	${INSTALL_PROGRAM} ${WRKSRC}/bin/scollector ${PREFIX}/bin/
.for sec in 1 5 7
	${INSTALL_MAN} ${WRKSRC}/man/*.${sec} ${PREFIX}/man/man${sec}/
.endfor

.include <bsd.port.mk>
