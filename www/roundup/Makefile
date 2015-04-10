# $OpenBSD$
COMMENT 		= flexible issue tracker

MODPY_EGG_VERSION 	= 1.5.0
DISTNAME 		= roundup-${MODPY_EGG_VERSION}
REVISION		=4

CATEGORIES 		= www

HOMEPAGE 		= http://roundup-tracker.org/

MAINTAINER 		= Alex Holst <a@mongers.org>

# BSD
PERMIT_PACKAGE_CDROM 	= Yes

MASTER_SITES 		= ${MASTER_SITE_PYPI:=r/roundup/}

MODULES 		= lang/python

RUN_DEPENDS 		= devel/py-tz

#.if ${FLAVOR:Mpostgresql}
# Really? psycopg2 depends on pg
# RUN_DEPENDS		+= databases/py-psycopg2
#.endif

HOMEDIR =		${VARBASE}/roundup

SUBST_VARS =		HOMEDIR

do-test:
	cd ${WRKSRC}; ${SETENV} ${MAKE_ENV} ${MODPY_BIN} run_tests.py

.include <bsd.port.mk>
