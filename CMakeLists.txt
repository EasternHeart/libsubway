project(LibHeartlenv)
cmake_minimum_required(VERSION 2.6)
find_package(Qt4 REQUIRED)

include_directories(${QT_INCLUDES} ${CMAKE_CURRENT_BINARY_DIR})

set(heartlenv_SRCS xfitman.cpp)
qt4_automoc(${heartlenv_SRCS})
add_library(heartlenv SHARED ${heartlenv_SRCS})
target_link_libraries(heartlenv ${QT_QTCORE_LIBRARY} ${QT_QTGUI_LIBRARY})
install(TARGETS heartlenv LIBRARY DESTINATION lib)
install(FILES xfitman.h DESTINATION include/libheartlenv)
