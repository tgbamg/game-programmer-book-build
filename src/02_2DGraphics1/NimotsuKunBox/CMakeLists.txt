cmake_minimum_required (VERSION 3.8)

set( PROJECT_NAME NimotsuKunBox )
set( SECTION_NAME 2DGraphics1 )

include( ../../cmake/SampleBase.cmake )

set_property(GLOBAL PROPERTY USE_FOLDERS ON)
set_target_properties(${PROJECT_NAME} PROPERTIES FOLDER 02_2DGraphics1 )

# File Copy
set( COPY_FILES stageData.txt )
include( ../../cmake/copyresource.cmake )

