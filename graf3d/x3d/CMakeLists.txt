############################################################################
# CMakeLists.txt file for building ROOT graf3d/x3d package
############################################################################

set(libname X3d)

include_directories(${X11_INCLUDE_DIR})

ROOT_GENERATE_DICTIONARY(G__X3d TViewerX3D.h TX3DFrame.h MODULE ${libname} LINKDEF LinkDef.h DEPENDENCIES Graf3d Gui)

ROOT_LINKER_LIBRARY(${libname} *.cxx *.c G__X3d.cxx LIBRARIES ${X11_LIBRARIES} DEPENDENCIES Graf3d Gui)
ROOT_INSTALL_HEADERS()
