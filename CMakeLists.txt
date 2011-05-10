cmake_minimum_required(VERSION 2.8)
project(osgQtBackport)

find_package(OpenSceneGraph COMPONENTS osgViewer osgGA osgWidget REQUIRED)
include_directories(${OPENSCENEGRAPH_INCLUDE_DIRS})

find_package(Qt4 COMPONENTS QtGui QtCore QtOpenGL REQUIRED)
include(${QT_USE_FILE})

include_directories(include)

add_subdirectory(src/osgQt)
