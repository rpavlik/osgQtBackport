ADD_DEFINITIONS(-DOSGQT_LIBRARY)

SET(LIB_NAME osgQt)
SET(HEADER_PATH ${PROJECT_SOURCE_DIR}/include/${LIB_NAME})

SET(SOURCES_H
   # ${HEADER_PATH}/QGraphicsViewAdapter
)

QT4_WRAP_CPP( SOURCES_H_MOC ${SOURCES_H} OPTIONS "-f" )


SET(LIB_PUBLIC_HEADERS
    ${HEADER_PATH}/Export
    ${HEADER_PATH}/GraphicsWindowQt
   # ${HEADER_PATH}/QFontImplementation
   # ${HEADER_PATH}/QGraphicsViewAdapter
   # ${HEADER_PATH}/QWidgetImage
   # ${HEADER_PATH}/QWebViewImage
)
INCLUDE_DIRECTORIES(${QT_INCLUDE_DIR} ${QT_QTCORE_INCLUDE_DIR})

# FIXME: For OS X, need flag for Framework or dylib
ADD_LIBRARY(${LIB_NAME}
    SHARED
    ${LIB_PUBLIC_HEADERS}
    GraphicsWindowQt.cpp
  #  QFontImplementation.cpp
  #  QGraphicsViewAdapter.cpp
  #  QWidgetImage.cpp
    ${SOURCES_H_MOC}
)


TARGET_LINK_LIBRARIES(${LIB_NAME} ${QT_QTCORE_LIBRARY} ${QT_QTGUI_LIBRARY} ${QT_QTOPENGL_LIBRARY} ${OPENSCENEGRAPH_LIBRARIES})
