# Created by: Lev Serebryakov <lev@FreeBSD.org>
# $FreeBSD$

PORTNAME=	vips
PORTVERSION=	8.7.0
DISTVERSIONPREFIX=	v
CATEGORIES=	graphics

MAINTAINER=	danilo@FreeBSD.org
COMMENT=	Free image processing system

LICENSE=	LGPL21
LICENSE_FILE=	${WRKSRC}/COPYING

BUILD_DEPENDS=	gtkdocize:textproc/gtk-doc
RUN_DEPENDS=	bash:shells/bash
LIB_DEPENDS=	libcfitsio.so:astro/cfitsio \
		liborc-0.4.so:devel/orc \
		libGraphicsMagick.so:graphics/GraphicsMagick \
		libIlmImf.so:graphics/openexr \
		liblcms2.so:graphics/lcms2 \
		libexif.so:graphics/libexif	\
		libpng.so:graphics/png \
		libtiff.so:graphics/tiff \
		libwebp.so:graphics/webp \
		libfftw3.so:math/fftw3 \
		libmatio.so:math/matio \
		libgirepository-1.0.so:devel/gobject-introspection \
		libfontconfig.so:x11-fonts/fontconfig \
		libfreetype.so:print/freetype2 \
		libgif.so:graphics/giflib \
		libpoppler-glib.so:graphics/poppler-glib \
		libImath.so:graphics/ilmbase \
		libhdf5.so:science/hdf5 \
		libexpat.so:textproc/expat2 \
		libcurl.so:ftp/curl

USES=		autoreconf:build compiler:c++11-lang cpe gettext gmake gnome jpeg libtool \
		pathfix pkgconfig python:2.7 shebangfix

USE_GITHUB=	yes
GH_ACCOUNT=	jcupitt
GH_PROJECT=	libvips

SHEBANG_FILES=	tools/vips-${PORTVERSION:R} tools/vipsprofile
USE_GNOME=	cairo gdkpixbuf2 glib20 libgsf librsvg2 libxml2 pango
GNU_CONFIGURE=	yes
CONFIGURE_SCRIPT=	./autogen.sh
CONFIGURE_ARGS+=	--without-x \
			--without-openslide \
			--with-magickpackage=GraphicsMagick
INSTALL_TARGET=	install-strip
USE_LDCONFIG=	yes

CPPFLAGS+=	-I${LOCALBASE}/include
LDFLAGS+=	-L${LOCALBASE}/lib

PLIST_SUB=	VERSION="${PORTVERSION:R}"

OPTIONS_DEFINE=		DOCS PYTHON
OPTIONS_DEFAULT=	PYTHON
OPTIONS_SUB=		yes

DOCS_CONFIGURE_ENABLE=	gtk-doc gtk-doc-html

PYTHON_CONFIGURE_ENABLE=	pyvips8
PYTHON_USE=			GNOME=pygobject3

.include <bsd.port.mk>
