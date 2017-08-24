project(ImageLib)

add_library(${PROJECT_NAME}
	wx.h
	GXImage.h
	GXImage.cpp)

add_dependencies(${PROJECT_NAME} wxWidgets)
ExternalProject_Get_Property(wxWidgets INSTALL_DIR)
	
target_include_directories(${PROJECT_NAME}
	PRIVATE ${INSTALL_DIR}/include
	PRIVATE ${INSTALL_DIR}/lib/vc140_dll/mswud
)

target_link_libraries(${PROJECT_NAME}
	debug		${INSTALL_DIR}/lib/vc140_dll/wxmsw31ud_core.lib
	debug	 	${INSTALL_DIR}/lib/vc140_dll/wxbase31ud.lib
	optimized	${INSTALL_DIR}/lib/vc140_dll/wxmsw31u_core.lib
	optimized	${INSTALL_DIR}/lib/vc140_dll/wxbase31u.lib
	)