project(ProtoWizard)

add_executable(${PROJECT_NAME} WIN32
AddStatusDlg.cpp 
  IDSetPage.h  
  NewItemDlg.h   
  ProtoWizardDlg.cpp
  StructEdit.cpp   
  VarListCtrl.h
AddStatusDlg.h   
  DataSetPage.cpp
  JavaCode.cpp   
  P2PDlg.cpp     
  ProtoWizard.cpp
  ProtoWizardDlg.h 
  StatusPage.cpp 
  StructEdit.h   
  VarsBut.cpp
BindStructDlg.cpp
  DataSetPage.h   
  JavaCode.h    
  P2PDlg.h      
  ReqModeDlg.cpp  
  StatusPage.h   
  StructEditDlg.cpp
  VarsBut.h
BindStructDlg.h  
  MsgDlg.cpp   
  PopList.cpp     
  ProtoWizard.h 
  ReqModeDlg.h    
  StdAfx.cpp    
  StructEditDlg.h
  WizzardDlg.cpp
ClassSetPage.cpp 
  MsgDlg.h    
  PopList.h    
  StdAfx.h      
  WizzardDlg.h
ClassSetPage.h   
  IDSetPage.cpp   
  NewItemDlg.cpp
  ProtoWizard.rc 
  Resource.h      
    VarListCtrl.cpp )

set_target_properties(${PROJECT_NAME}
	PROPERTIES
	LINK_FLAGS "/level='highestAvailable' /SAFESEH:NO")

target_link_libraries(${PROJECT_NAME}
			WinBase)