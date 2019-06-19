cmake_minimum_required(VERSION 3.0)
project(pytorch11)

set(CMAKE_PREFIX_PATH "${CMAKE_CURRENT_SOURCE_DIR}/libtorch")
find_package(Torch REQUIRED)
include_directories("${TORCH_INCLUDE_DIRS}")

find_package( OpenCV REQUIRED )
include_directories( ${OpenCV_INCLUDE_DIRS} )

add_executable(example-app example-app.cpp)
target_link_libraries(example-app ${TORCH_LIBRARIES} ${OpenCV_LIBS})
set_property(TARGET example-app PROPERTY CXX_STANDARD 11)
