cmake_minimum_required(VERSION 3.5)
project(test_pytorch)
set(CMAKE_BUILD_TYPE Debug)

set(CMAKE_CXX_STANDARD 17) #设置为C++11，可能报错
set(Torch_DIR /home/an/sdk/libtorch/share/cmake/Torch) #确定.cmake文件的地址
find_package(Torch REQUIRED)  
message(STATUS "Torch library status:")
message(STATUS "    include path: ${TORCH_INCLUDE_DIRS}")
message(STATUS "    lib path : ${TORCH_LIBRARIES} ")

add_executable(example-app example-app.cpp)
target_link_libraries(example-app "${TORCH_LIBRARIES}")