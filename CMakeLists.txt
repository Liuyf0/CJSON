cmake_minimum_required (VERSION 2.6)

project (leptjson_test C)

# 添加头文件
include_directories(${CMAKE_SOURCE_DIR}/include)
# 设置可执行文件生成目录
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_SOURCE_DIR}/bin)
# 设置库生成目录
set(LIBRARY_OUTPUT_PATH ${CMAKE_SOURCE_DIR}/lib)

add_library(libleptjson ${CMAKE_SOURCE_DIR}/src/leptjson.c ${CMAKE_SOURCE_DIR}/include/leptjson.h)

add_executable(leptjson_test ${CMAKE_SOURCE_DIR}/tests/test.c)

target_link_libraries(leptjson_test libleptjson)