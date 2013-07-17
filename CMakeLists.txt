PROJECT(pvr.iptvsimple)

CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

ENABLE_LANGUAGE(CXX)

FIND_PACKAGE(xbmc REQUIRED)
FIND_PACKAGE(xbmcplatform REQUIRED)
FIND_PACKAGE(ZLIB REQUIRED)

addon_version(pvr.iptvsimple IPTV)

INCLUDE_DIRECTORIES(${xbmcplatform_INCLUDE_DIRS}
                    ${XBMC_INCLUDE_DIR}
                    ${ZLIB_INCLUDE_DIRS}
                    ${PROJECT_SOURCE_DIR}/lib)

SET(DEPLIBS ${xbmcplatform_LIBRARIES}
            ${ZLIB_LIBRARIES})

SET(SOURCES src/client.cpp
            src/PVRIptvData.cpp)

build_addon(pvr.iptvsimple SOURCES DEPLIBS IPTV_VERSION)

install_addon(pvr.iptvsimple ${IPTV_VERSION})
