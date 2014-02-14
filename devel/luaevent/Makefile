# Created by: Benjamin Podszun <dar@darklajid.de>

PORTNAME=	luaevent
PORTVERSION=	0.4.3
CATEGORIES=	devel
PKGNAMEPREFIX=	${LUA_PKGNAMEPREFIX}

MAINTAINER=	dar@darklajid.de
COMMENT=	libevent bindings for lua

LICENSE=	MIT

USE_GITHUB=	yes
GH_ACCOUNT=	harningt
GH_PROJECT=	${PORTNAME}
GH_TAGNAME=	v${PORTVERSION}
GH_COMMIT=	724e1f1

USE_GMAKE=	yes
USE_LUA?=	5.1
LUA_COMPS=	lua

BUILD_DEPENDS=	pkgconf:${PORTSDIR}/devel/pkgconf
LIB_DEPENDS=	libevent.so:${PORTSDIR}/devel/libevent2

CFLAGS+=	`pkgconf --cflags lua-${LUA_VER}` \
		`pkgconf --cflags libevent` \
		-I${LUA_INCDIR}
LDFLAGS+=	-shared -L${LOCALBASE}/lib \
		`pkgconf --libs lua-${LUA_VER}` \
		`pkgconf --libs libevent`
MAKE_ENV+=	INSTALL_DIR_LUA=${LUA_MODSHAREDIR} INSTALL_DIR_BIN=${LUA_MODLIBDIR}

post-extract:
	@${REINPLACE_CMD} -e 's/CFLAGS[[:blank:]]*=/CFLAGS\+=/g' ${WRKSRC}/Makefile
	@${REINPLACE_CMD} -e 's/LDFLAGS[[:blank:]]*=/LDFLAGS\+=/g' ${WRKSRC}/Makefile

.include <bsd.port.mk>
