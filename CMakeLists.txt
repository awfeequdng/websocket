CMAKE_MINIMUM_REQUIRED(VERSION 3.17.3)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)


project(websocket)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/contrib/websocketpp)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/contrib/boost_1_80_0)

set(CMAKE_BUILD_TYPE Release)

SET (CMAKE_CXX_STANDARD 17)

# include generated files in project environment
include_directories(
  ${PROJECT_SOURCE_DIR}
)

# Get the list of all pxtidb sources.
file(GLOB_RECURSE
        WEBSOCKET_SRCS                  # Store the list of files into the variable ${WEBSOCKET_SRCS}.
        CONFIGURE_DEPENDS               # See above. Ask CMake to regenerate the build system if these files change.
        ${PROJECT_SOURCE_DIR}/src/*.cpp
        ${PROJECT_SOURCE_DIR}/src/*.h
        )

add_executable(websocket
  ${WEBSOCKET_SRCS}
)


