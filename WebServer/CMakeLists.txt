project(WebServer)

add_executable(${PROJECT_NAME} WIN32
   reqsock.cpp
     request.h 
	   StdAfx.cpp 
 SVR.h      
     WebServer.cpp
	     WebServer1.h
PayPostClient.cpp 
 reqsock.h  
	    StdAfx.h  
    WebServer.rc  
	  WebServerDlg.cpp
PayPostClient.h 
   request.cpp 
    Resource.h 
	 SVR.cpp   
   WebServer.h  
     WebServer1.cpp 
	  WebServerDlg.h )
	  
set_target_properties(${PROJECT_NAME}
	PROPERTIES
	LINK_FLAGS "/SAFESEH:NO")

target_link_libraries(${PROJECT_NAME}
			GoBase)