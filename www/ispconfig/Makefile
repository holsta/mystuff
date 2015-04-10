# $OpenBSD$

COMMENT =		hosting control panel software

VERSION =		3.0.5.3
DISTNAME =		ISPConfig-${VERSION}
PKG_NAME =		ispconfig-${VERSION}
PKG_NAME-dashboard =	ispconfig-dashboard-${VERSION}
PKG_NAME-db=		ispconfig-db-${VERSION}
PKG_NAME-mail=		ispconfig-mail-${VERSION}
PKG_NAME-apache=	ispconfig-apache$-{VERSION}
PKG_NAME-nginx=		ispconfig-nginx-${VERSION}

# Would be nice to have various packages that only install a subset: 
# -dashboard: ISPConfig UI only
# -db: MySQL only, configured to handle ISPConfig
# -mail: Postfix, IMAP, POP3 only
# -apache: Apache2+sftp only
# -nginx: Nginx+sftp only

CATEGORIES =	www 

HOMEPAGE =	http://www.ispconfig.org/

MAINTAINER =	Alex Holst <a@mongers.org>

# BSD
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =	${MASTER_SITE_SOURCEFORGE:=ispconfig/}

NO_BUILD = Yes
NO_TEST = Yes

MODULES =	lang/php
RUN_DEPENDS =	lang/php/${MODPHP_VERSION},-mysqli

PREFIX =		/var/www
HOMEDIR =		${PREFIX}/ispconfig

#SUBST_VARS +=		HOMEDIR

do-install:
	${INSTALL_DATA_DIR} ${HOMEDIR}/
	(cd ${WRKSRC}/../ispconfig3_install/; pax -rw ./ ${HOMEDIR})

.include <bsd.port.mk>
