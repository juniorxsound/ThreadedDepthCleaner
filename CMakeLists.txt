# CMake minimum version requirement
cmake_minimum_required(VERSION 2.8)

# Name
project( DepthCleaner )

### Compilation flags: adapt to your needs ###
if(MSVC)
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /MP /bigobj") ### Enable parallel compilation
  set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_DEBUG ${CMAKE_BINARY_DIR} )
  set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_RELEASE ${CMAKE_BINARY_DIR} )
else()
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
endif()

# Locate the OpenCV lib
find_package( OpenCV REQUIRED )

# RealSense lib
set(DHWM_OVER_XU          OFF)
set(BUILD_EXAMPLES     OFF)

# Add the configurations from librealsense
add_subdirectory("${CMAKE_CURRENT_SOURCE_DIR}/ext/librealsense")

# Add referecne
include_directories("${CMAKE_CURRENT_SOURCE_DIR}/ext/librealsense/include")

# Compile all the cpp files in src
file(GLOB SOURCES
"${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp"
)

# Build an executable
add_executable(${PROJECT_NAME} ${SOURCES})

# Link the OpenCV lib
target_link_libraries( DepthCleaner ${OpenCV_LIBS} realsense2 )
