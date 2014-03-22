# Created by: Benjamin Podszun <dar@darklajid.de>

PORTNAME=	lua-zlib
PORTVERSION=	0.3.0
CATEGORIES=	archivers
PKGNAMEPREFIX=	${LUA_PKGNAMEPREFIX}

MAINTAINER=	dar@darklajid.de
COMMENT=	zlib bindings for lua

LICENSE=	MIT

USES=		pkgconfig
USE_GITHUB=	yes
GH_ACCOUNT=	brimworks
GH_PROJECT=	${PORTNAME}
GH_COMMIT=	c0014bc
GH_TAGNAME=	${GH_COMMIT}

USE_LUA?=	5.1
LUA_COMPS=	lua

PLIST_FILES=	${LUA_MODLIBDIR}/zlib.so

do-build:
	${CC} -fPIC -shared -o ${WRKSRC}/zlib.so -I${LUA_INCDIR} \
		-L${LUA_LIBDIR} -llua -lm -lz ${WRKSRC}/lua_zlib.c

do-install:
	${MKDIR} ${STAGEDIR}/${LUA_MODLIBDIR}
	${INSTALL_PROGRAM} ${WRKSRC}/zlib.so ${STAGEDIR}/${LUA_MODLIBDIR}

.include <bsd.port.mk>
