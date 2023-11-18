cmake_minimum_required(VERSION 3.5)
project(yoloncnn VERSION 0.1.0 LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

find_package(OpenCV REQUIRED)

set(ncnn_DIR "~/library/ncnn-20231027-ubuntu-2204/lib/cmake/ncnn" CACHE PATH "Directory that contains ncnnConfig.cmake")

find_package(ncnn REQUIRED)

include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(yoloncnn main.cpp face.cpp)

target_link_libraries(yoloncnn ncnn ${OpenCV_LIBS})