# Created by: Benjamin Podszun <dar@darklajid.de>

PORTNAME=	lua-zlib
PORTVERSION=	0.3.0
CATEGORIES=	archivers
PKGNAMEPREFIX=	${LUA_PKGNAMEPREFIX}

MAINTAINER=	dar@darklajid.de
COMMENT=	zlib bindings for lua

LICENSE=	MIT

USES=		lua:51 pkgconfig
USE_GITHUB=	yes
GH_ACCOUNT=	brimworks
GH_PROJECT=	${PORTNAME}
GH_COMMIT=	c0014bc
GH_TAGNAME=	${GH_COMMIT}

PLIST_FILES=	${LUA_MODLIBDIR}/zlib.so

do-build:
	${CC} -fPIC -shared -o ${WRKSRC}/zlib.so \
		`pkgconf --cflags lua-${LUA_VER}` \
                `pkgconf --libs lua-${LUA_VER}` \
		-llua -lm -lz ${WRKSRC}/lua_zlib.c

do-install:
	${MKDIR} ${STAGEDIR}/${LUA_MODLIBDIR}
	${INSTALL_PROGRAM} ${WRKSRC}/zlib.so ${STAGEDIR}/${LUA_MODLIBDIR}

.include <bsd.port.mk>
