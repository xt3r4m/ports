# Created by: Danilo Egea Gondolfo <danilo@FreeBSD.org>
# $FreeBSD$

PORTNAME=	fs-uae
PORTVERSION=	2.4.1
PORTREVISION=	5
CATEGORIES=	emulators
MASTER_SITES=	http://fs-uae.net/stable/${PORTVERSION}/

MAINTAINER=	tomse@oagd.net
COMMENT=	Amiga emulator

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS=	libpng.so:graphics/png \
		libopenal.so:audio/openal-soft

USE_HARDENING=	pie:off relro:off

USES=		gettext gmake pkgconfig
USE_SDL=	sdl
USE_GL=		gl
USE_GNOME=	glib20
LLD_UNSAFE=	yes
INSTALLS_ICONS=	yes
MAKE_ARGS+=	prefix=${PREFIX}

OPTIONS_DEFINE=	DOCS

.include <bsd.port.mk>
