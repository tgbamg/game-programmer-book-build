cmake_minimum_required (VERSION 3.8)

set( PROJECT_NAME BakudanBitoUsingHardware )
set( SECTION_NAME 3DHardware1 )


include( "../../cmake/SampleBase2.cmake" )

# Project Codes
file(GLOB SRCS 
  ${CMAKE_CURRENT_SOURCE_DIR}/*.h
  ${CMAKE_CURRENT_SOURCE_DIR}/*.cpp
 )
file(GLOB SEQ_SRCS 
  ${CMAKE_CURRENT_SOURCE_DIR}/Sequence/*.h
  ${CMAKE_CURRENT_SOURCE_DIR}/Sequence/*.cpp
)

file(GLOB SEQ_GAME_SRCS 
  ${CMAKE_CURRENT_SOURCE_DIR}/Sequence/Game/*.h
  ${CMAKE_CURRENT_SOURCE_DIR}/Sequence/Game/*.cpp
)

file(GLOB GAME_SRCS 
  ${CMAKE_CURRENT_SOURCE_DIR}/Game/*.h
  ${CMAKE_CURRENT_SOURCE_DIR}/Game/*.cpp
)

add_executable( 
  ${PROJECT_NAME} WIN32 
  ${SRCS} ${SEQ_SRCS} ${SEQ_GAME_SRCS} ${GAME_SRCS}
)

target_link_libraries( ${PROJECT_NAME} debug GameLib_d )
target_link_libraries( ${PROJECT_NAME} optimized GameLib )

set_property(GLOBAL PROPERTY USE_FOLDERS ON)
set_target_properties(${PROJECT_NAME} PROPERTIES FOLDER 13_3DHardware )

source_group( "Sequence" FILES ${SEQ_SRCS} )



# File Copy
set( COPY_DIRS data )
include( ../../cmake/copyresource.cmake )

