# $FreeBSD$

PORTNAME=	trueos-utils-qt5
PORTVERSION=	201806221247
CATEGORIES=	sysutils

MAINTAINER=	jt@ixsystems.com
COMMENT=	TrueOS QT5 Utilities

LICENSE=	BSD2CLAUSE

RUN_DEPENDS=	setxkbmap:x11/setxkbmap \
		xdpyinfo:x11/xdpyinfo \
		xwd:x11/xwd \
		xcursor-themes>=0:x11-themes/xcursor-themes
LIB_DEPENDS=	libtrueos-ui.so:sysutils/trueos-libqt5

WRKSRC_SUBDIR=  src-qt5
MAKE_ARGS=      PREFIX=${STAGEDIR}${PREFIX}

CONFLICTS=      pcbsd-utils-[0-9]*

MAKE_JOBS_UNSAFE=yes
ONLY_FOR_ARCHS= amd64
USE_LDCONFIG=   yes
USE_QT=        core gui network svg linguist_build \
		buildtools_build x11extras widgets multimedia
USES=           qmake shebangfix tar:xz qt:5
USE_GL+=	gl

WRKSRC_SUBDIR=  src-qt5

QMAKE_ARGS=     CONFIG+="configure"

USE_GITHUB=	yes
GH_ACCOUNT=	trueos
GH_PROJECT=	trueos-utils-qt5
GH_TAGNAME=	d2f261fb28aa1def82d2ec7826abc6bc7f109c90

.include <bsd.port.mk>
