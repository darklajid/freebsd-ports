# Created by: Andrew Lewis <freeghb@gmail.com>
# $FreeBSD: head/textproc/luaexpat/Makefile 341652 2014-01-28 20:16:01Z lx $

PORTNAME=	luaexpat
PORTVERSION=	1.3.0
CATEGORIES=	textproc
MASTER_SITES=	http://matthewwild.co.uk/projects/luaexpat/ \
				http://redundancy.redundancy.org/mirror/
PKGNAMEPREFIX=	${LUA_PKGNAMEPREFIX}

MAINTAINER=	lx@FreeBSD.org
COMMENT=	LuaExpat is a SAX XML parser based on the Expat library

LIB_DEPENDS=	expat.6:${PORTSDIR}/textproc/expat2

USES=		gmake
ALL_TARGET=	lib
USE_LUA=	5.1-5.2
WANT_LUA_VER=	5.1

CFLAGS+=	-fPIC
LDFLAGS+=	-L${LOCALBASE}/lib
MAKE_ENV=	LUA_CDIR=${LUA_MODLIBDIR} LUA_LDIR=${LUA_MODSHAREDIR} LUA_INC="-I${LUA_INCDIR}" EXPAT_INC="-I${LOCALBASE}/include"

.include <bsd.port.mk>
