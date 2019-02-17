# $OpenBSD: Makefile,v 1.24 2019/02/07 15:50:09 edd Exp $

COMMENT =	ratcheting forward secrecy protocol

GH_ACCOUNT =	signalapp
GH_PROJECT =	libsignal-protocol-c
GH_TAGNAME =	v2.3.2

CATEGORIES =	net
HOMEPAGE =	https://signal.org/

MAINTAINER =	Alex Holst <a@mongers.org>

# GPL 3 
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += c pthread

RUN_DEPENDS = devel/protobuf-c

MODULES = devel/cmake

TEST_DEPENDS = devel/check

CONFIGURE_ARGS = -DBUILD_TESTING=ON


.include <bsd.port.mk>
