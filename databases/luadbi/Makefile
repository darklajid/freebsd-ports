# Created by: Benjamin Podszun<dar@darklajid.de>

PORTNAME=	luadbi
PORTVERSION=	0.5
CATEGORIES=	databases
MASTER_SITES=	https://luadbi.googlecode.com/files/
DISTNAME=	${PORTNAME}.${PORTVERSION}
PKGNAMEPREFIX=	${LUA_PKGNAMEPREFIX}
WRKSRC=		${WRKDIR}
LICENSE=	MIT

MAINTAINER=	dar@darklajid.de
COMMENT=	Lua interface library to connect to various databases

FETCH_ARGS=	-Fpr

ALL_TARGET=	free
USE_GMAKE=	yes
CFLAGS=		-g -pedantic -Wall -O2 -fpic \
		-I/usr/local/include/mysql \
		-I/usr/local/include/postgresql/internal \
		`pkgconf --cflags sqlite3` \
		`pkgconf --cflags lua-${LUA_VER}` \
		-I.
LDFLAGS+=	-shared -L/usr/local/lib \
		`pkgconf --libs lua-${LUA_VER}` \
		-L/usr/local/lib/mysql
MAKE_ENV=	COMMON_LDFLAGS="${LDFLAGS}" \
		INSTALL_DIR_LUA=${LUA_MODSHAREDIR} INSTALL_DIR_BIN=${LUA_MODLIBDIR}
USE_LUA=	5.1
WANT_LUA_VER=	5.1
#USE_OPENSSL=	yes
USE_MYSQL=	yes
USE_PGSQL=	yes
USE_SQLITE=	yes

.include <bsd.port.options.mk>

.include <bsd.port.mk>
