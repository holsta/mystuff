
COMMENT    =	modular irc server

GH_PROJECT =	inspircd
GH_ACCOUNT = 	inspircd
GH_TAGNAME =	v3.0.0a10

CATEGORIES = 	net
HOMEPAGE = 	https://www.inspircd.org/

MAINTAINER = 	Alex Holst <a@mongers.org>

PERMIT_PACKAGE_CDROM =	Yes

RUN_DEPENDS = 		databases/sqlite
BUILD_DEPENDS =		devel/cmake

USE_GMAKE	=	Yes
#SEPARATE_BUILD = 	flavored
CONFIGURE_STYLE = 	simple
CONFIGURE_ARGS += 	--development
CONFIGURE_ARGS +=       --system
CONFIGURE_ARGS +=       --distribution-label=OpenBSD
CONFIGURE_ARGS +=	--enable-extras=m_sqlite3.cpp
CONFIGURE_ARGS +=	--enable-extras=m_ssl_openssl.cpp

post-configure:
	ls ${WRKDIST}
	ls ${WRKDIR}

.include <bsd.port.mk>
