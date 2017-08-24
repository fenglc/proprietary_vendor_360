project(robot)

add_executable(${PROJECT_NAME}
	main.cpp
	configurable.h
	configurable.cpp
	launcher.h
	launcher.cpp
	robot.h
	robot.cpp
	pipe.h
	pipe.cpp
	utility.h
	utility.cpp
	 )
	 
set_target_properties(${PROJECT_NAME}
	PROPERTIES
	LINK_FLAGS "/SAFESEH:NO /NODEFAULTLIB:LIBCMT")
	
target_link_libraries(${PROJECT_NAME}
	GoBase)

add_dependencies(${PROJECT_NAME} argtable3)
ExternalProject_Get_Property(argtable3 SOURCE_DIR)
target_include_directories(${PROJECT_NAME}
	PRIVATE ${SOURCE_DIR})

ExternalProject_Get_Property(argtable3 INSTALL_DIR)
target_link_libraries(${PROJECT_NAME} ${INSTALL_DIR}/argtable3.lib)

add_dependencies(${PROJECT_NAME} iniparser)
ExternalProject_Get_Property(iniparser SOURCE_DIR)
target_include_directories(${PROJECT_NAME}
	PRIVATE ${SOURCE_DIR}/src)

ExternalProject_Get_Property(iniparser INSTALL_DIR)
target_link_libraries(${PROJECT_NAME} ${INSTALL_DIR}/iniparser.lib)
	
add_dependencies(${PROJECT_NAME} libevent)
ExternalProject_Get_Property(libevent SOURCE_DIR)
target_include_directories(${PROJECT_NAME}
	PRIVATE ${SOURCE_DIR}/include
	PRIVATE ${SOURCE_DIR}/WIN32-Code/nmake)

ExternalProject_Get_Property(libevent INSTALL_DIR)
target_link_libraries(${PROJECT_NAME} ${INSTALL_DIR}/libevent.lib)