cmake_minimum_required(VERSION 3.14)

SET(PROJECT_NAME OVOPlayer)
project(${PROJECT_NAME})


add_definitions(-D_DEBUG )

ADD_DEFINITIONS(-DUNICODE)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_DEBUG_POSTFIX "d")

include_directories(../share/include)


link_directories(../share/lib)

if (_DEBUG)
   link_directories(../share/lib)
else()
  link_directories(../share/lib)
endif()

file(GLOB HEADER_FILES *.h)
file(GLOB SOURCE_FILES *.cpp)
set(DIR_FILES
	${HEADER_FILES}
	${SOURCE_FILES}
)


ADD_EXECUTABLE(
	${PROJECT_NAME} 
	${DIR_FILES}
)



target_link_libraries(${PROJECT_NAME} 
		debug avcodec  optimized avcodec
	)  