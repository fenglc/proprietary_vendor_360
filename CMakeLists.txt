cmake_minimum_required(VERSION 3.6)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
set_property(GLOBAL PROPERTY USE_FOLDERS ON)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /wd4996")
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} /Gm /ZI")

add_subdirectory(GoBase)
add_subdirectory(3rdparty)
add_subdirectory(ImageLib)
add_subdirectory(ServerDaemon)
add_subdirectory(robot)

add_definitions(-D_AFXDLL)
set(CMAKE_MFC_FLAG 2)
add_definitions(-DNO_WARN_MBCS_MFC_DEPRECATION)

add_subdirectory(WinBase)
add_subdirectory(GoGame)
add_subdirectory(GoServer)
add_subdirectory(WebServer)
add_subdirectory(DataDesign)
add_subdirectory(ProtoWizard)

remove_definitions(-DNO_WARN_MBCS_MFC_DEPRECATION)
remove_definitions(-D_AFXDLL)
unset(CMAKE_MFC_FLAG)
