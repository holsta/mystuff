
COMMENT    =	modular nickserv/etc services for IRC

GH_PROJECT =	anope
GH_ACCOUNT = 	anope
GH_TAGNAME =	2.0.6

CATEGORIES = 	net
HOMEPAGE = 	https://www.anope.org/

MAINTAINER = 	Alex Holst <a@mongers.org>

PERMIT_PACKAGE_CDROM =	Yes

RUN_DEPENDS = 		databases/sqlite

USE_GMAKE	=	Yes
SEPARATE_BUILD = 	flavored
#CONFIGURE_STYLE = 	gnu	
CONFIGURE_ARGS += 	--disable-interactive
CONFIGURE_ARGS +=	--socketengine=kqueue
CONFIGURE_ARGS +=	--disable-extras=gnutls

pre-configure:
	cd ${WRKDIST}; ./Config -nointro -quick

.include <bsd.port.mk>
