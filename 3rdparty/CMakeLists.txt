include(ExternalProject)

ExternalProject_Add(argtable3
	PREFIX argtable3
	URL ${CMAKE_CURRENT_SOURCE_DIR}/argtable3-3.0.1.tar.gz
	PATCH_COMMAND ${CMAKE_COMMAND} -E copy_if_different ${CMAKE_CURRENT_SOURCE_DIR}/patches/argtable3/Makefile.nmake Makefile.nmake
	CONFIGURE_COMMAND ""
	BUILD_COMMAND nmake /f Makefile.nmake static_lib
	BUILD_IN_SOURCE 1
	INSTALL_COMMAND ${CMAKE_COMMAND} -E rename argtable3.lib <INSTALL_DIR>/argtable3.lib
)

ExternalProject_Add(iniparser
	PREFIX iniparser
	URL ${CMAKE_CURRENT_SOURCE_DIR}/iniparser-3.2.tar.gz
	PATCH_COMMAND  ${CMAKE_COMMAND} -E copy_if_different ${CMAKE_CURRENT_SOURCE_DIR}/patches/iniparser/Makefile.nmake Makefile.nmake
	CONFIGURE_COMMAND ""
	BUILD_COMMAND nmake /f Makefile.nmake static_lib
	BUILD_IN_SOURCE 1
	INSTALL_COMMAND  ${CMAKE_COMMAND} -E rename iniparser.lib <INSTALL_DIR>/iniparser.lib
)

ExternalProject_Add(libevent
	PREFIX libevent
	URL ${CMAKE_CURRENT_SOURCE_DIR}/libevent-2.1.8-stable.tar.gz
	CONFIGURE_COMMAND ""
	BUILD_COMMAND nmake /f Makefile.nmake static_libs
	BUILD_IN_SOURCE 1
	INSTALL_COMMAND ${CMAKE_COMMAND} -E rename libevent.lib <INSTALL_DIR>/libevent.lib
)

ExternalProject_Add(wxWidgets
	PREFIX wxWidgets
	URL ${CMAKE_CURRENT_SOURCE_DIR}/wxWidgets-3.1.0.zip
	UPDATE_DISCONNECTED 1
	CONFIGURE_COMMAND ""
	BUILD_COMMAND ""
	BUILD_IN_SOURCE 1
	INSTALL_COMMAND ${CMAKE_COMMAND} -E remove_directory <INSTALL_DIR>/lib
		COMMAND ${CMAKE_COMMAND} -E remove_directory <INSTALL_DIR>/include
		COMMAND ${CMAKE_COMMAND} -E rename lib <INSTALL_DIR>/lib
		COMMAND ${CMAKE_COMMAND} -E rename include <INSTALL_DIR>/include
)