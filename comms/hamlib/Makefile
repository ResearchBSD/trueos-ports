# Created by: Sebastian Yepes <esn@x123.info>
# $FreeBSD$

PORTNAME=	hamlib
PORTVERSION=	3.1
PORTREVISION=	2
CATEGORIES=	comms hamradio
MASTER_SITES=	SF

MAINTAINER=	hamradio@FreeBSD.org
COMMENT=	Shared libraries for Amateur Radio Equipment Control Applications

LICENSE=	LGPL20

BUILD_DEPENDS=	swig3.0:devel/swig30
LIB_DEPENDS=	libltdl.so:devel/libltdl

INFO=		hamlib
USES=		autoreconf libtool:keepla pathfix perl5 pathfix pkgconfig python shebangfix tcl
USE_PYTHON=	py3kplist
SHEBANG_FILES=	bindings/perltest.pl
USE_PERL5=	build run
USE_GNOME=	libxml2
USE_LDCONFIG=	yes
# $TCL_INCLUDE_SPEC
CPPFLAGS+=	-I${LOCALBASE}/include
LIBS+=		-L${LOCALBASE}/lib
GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--with-perl-binding \
		--with-tcl-binding --with-tcl=${TCL_LIBDIR} \
		--with-python-binding --without-rigmatrix
PLIST_SUB=	VER=${PORTVERSION} TCL_VER=${TCL_VER}
INSTALL_TARGET=	install-strip
BINARY_ALIAS=	swig=swig3.0

OPTIONS_DEFINE=	DOCS

post-patch:
	@${REINPLACE_CMD} -e 's|%%PYTHON_SITELIBDIR%%|${PYTHON_SITELIBDIR}|g' \
		-e 's|%%TCL_LIBDIR%%|${TCL_LIBDIR}|g' \
		${WRKSRC}/bindings/Makefile.am
	@${REINPLACE_CMD} -e 's|%%TCLSH%%|${TCLSH}|g' \
		${WRKSRC}/bindings/tcltest.tcl
post-build:
	${PERL5} -pi -e 's/ doc_(perl|site|\$$\(INSTALLDIRS\))_install$$//' \
		${STAGEDIR}${WRKSRC}/bindings/Hamlib-pl.mk

post-install:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
.for d in ${WRKSRC}/AUTHORS ${WRKSRC}/COPYING ${WRKSRC}/COPYING.LIB \
		${WRKSRC}/ChangeLog ${WRKSRC}/INSTALL ${WRKSRC}/LICENSE \
		${WRKSRC}/NEWS ${WRKSRC}/PLAN ${WRKSRC}/README \
		${WRKSRC}/README.betatester ${WRKSRC}/README.win32 \
		${WRKSRC}/THANKS
	${INSTALL_DATA} ${WRKSRC}/${d} ${STAGEDIR}${DOCSDIR}
.endfor

.include <bsd.port.mk>
