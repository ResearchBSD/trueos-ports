# Created by: Kubilay Kocak <koobs@FreeBSD.org>
# $FreeBSD$

PORTNAME=	twitter
PORTVERSION=	1.18.0
DISTVERSIONPREFIX=	${PORTNAME}-
CATEGORIES=	net python
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
PKGNAMESUFFIX=	-tools

MAINTAINER=	koobs@FreeBSD.org
COMMENT=	Python API and command-line toolset for Twitter

TEST_DEPENDS=	${PYTHON_PKGNAMEPREFIX}nose>0:devel/py-nose@${PY_FLAVOR}

BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}pypandoc>0:textproc/py-pypandoc@${PY_FLAVOR}

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE

USES=		python:2.7-3.6
USE_PYTHON=	distutils concurrent autoplist
USE_GITHUB=	yes

GH_ACCOUNT=	sixohsix

NO_ARCH=	yes

do-test:
	@cd ${WRKSRC} && ${PYTHON_CMD} ${PYDISTUTILS_SETUP} test

.include <bsd.port.mk>
