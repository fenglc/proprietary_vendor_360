project(ServerDaemon)

add_executable(${PROJECT_NAME}
	Probe.h
	Probe.cpp
	main.cpp
)

set_target_properties(${PROJECT_NAME}
	PROPERTIES
	LINK_FLAGS "/level='highestAvailable' /SAFESEH:NO  /NODEFAULTLIB:LIBCMT")

target_link_libraries(${PROJECT_NAME}
	GoBase )

add_dependencies(${PROJECT_NAME} argtable3)
ExternalProject_Get_Property(argtable3 SOURCE_DIR)
target_include_directories(${PROJECT_NAME}
	PRIVATE ${SOURCE_DIR})

ExternalProject_Get_Property(argtable3 INSTALL_DIR)
target_link_libraries(${PROJECT_NAME}	${INSTALL_DIR}/argtable3.lib)

add_dependencies(${PROJECT_NAME} iniparser)
ExternalProject_Get_Property(iniparser SOURCE_DIR)
target_include_directories(${PROJECT_NAME}
	PRIVATE ${SOURCE_DIR}/src)

ExternalProject_Get_Property(iniparser INSTALL_DIR)
target_link_libraries(${PROJECT_NAME}	${INSTALL_DIR}/iniparser.lib)
