# $OpenBSD: Makefile,v 1.24 2019/02/07 15:50:09 edd Exp $

COMMENT =	ratcheting forward secrecy protocol

V =		2.3.2
DISTNAME =	libsignal-protocol-c-${V}
DISTFILES =	v${V}${EXTRACT_SUFX}

CATEGORIES =	net
HOMEPAGE =	https://signal.org/

MAINTAINER =	Alex Holst <a@mongers.org>

# GPL 3 
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += c pthread

RUN_DEPENDS = devel/cmake \
	      devel/protobuf-c

TEST_DEPENDS = devel/check 

MASTER_SITES = https://github.com/signalapp/libsignal-protocol-c/archive/

#WRKDIST =		${WRKDIR}/syncthing
#WRKSRC =		${WRKDIR}/go/src/github.com/syncthing/syncthing
SUBST_VARS +=		VARBASE


do-build:
	mkdir -p ${WRKSRC}/build && cd ${WRKSRC}/build && \
		cmake -DCMAKE_BUILD_TYPE=Debug .. && \
	       	${MAKE}

do-test:
	mkdir -p ${WRKSRC}/build && cd ${WRKSRC}/build && \
		cmake -DCMAKE_BUILD_TYPE=Debug -DBUILD_TESTING=1 .. && \
		cd tests && ${MAKE} && \
		cd .. && ctest

do-install:
	install ${WRKSRC}/build/src/libsignal-protocol-c.a ${PREFIX}/lib

.include <bsd.port.mk>
