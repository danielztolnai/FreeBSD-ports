# Created by: Rusmir Dusko <nemysis@FreeBSD.org>
# $FreeBSD$

PORTNAME=	viewnior
PORTVERSION=	1.6
DISTVERSIONPREFIX=	${PORTNAME}-
PORTREVISION=	6
CATEGORIES=	graphics

MAINTAINER=	portmaster@BSDforge.com
COMMENT=	Fast and simple image viewer

LICENSE=	GPLv3

LIB_DEPENDS=	libexiv2.so:graphics/exiv2

USES=		autoreconf compiler:c++11-lang desktop-file-utils gettext-tools \
		gmake gnome libtool pkgconfig

USE_GITHUB=	yes
GH_ACCOUNT=	hellosiyan
GH_PROJECT=	Viewnior

USE_GNOME=	glib20 gtk20 gdkpixbuf2 intltool intlhack
GNU_CONFIGURE=	yes
CPPFLAGS+=	-I${LOCALBASE}/include
LIBS+=		-L${LOCALBASE}/lib
INSTALLS_ICONS=	yes

PORTDOCS=	AUTHORS NEWS README

OPTIONS_DEFINE=	DOCS NLS
OPTIONS_SUB=	yes

NLS_USES=	gettext-runtime

pre-configure:
	${MKDIR} ${WRKSRC}/m4

post-install:
	${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${PORTDOCS:S|^|${WRKSRC}/|} ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
