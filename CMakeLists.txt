# CMake最低版本号要求
cmake_minimum_required(VERSION 3.0)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON) # For clang-tidy.
set(BUILD_SHARED_LIBS OFF) # We expect external libraries to be linked statically.
set(CMAKE_CXX_STANDARD 17) # Compile as C++17.
set(CMAKE_CXX_STANDARD_REQUIRED ON) # Require C++17 support.

project(downloader)

# find_package(CURL)

# # 递归遍历获取项目的所有源文件列表
# file(GLOB_RECURSE SRC_LIST FOLLOW_SYMLINKS main.cpp src/*.cpp)

# # 生成可执行文件 main，后面是源码列表
# add_executable(main ${SRC_LIST})
# # target_include_directories(main PRIVATE /usr/local/curl/include/curl)
# # target_link_libraries(main /usr/local/curl/lib/libcurl.so)
# target_link_libraries(main curl)


## 1.头文件目录
set(SAKURA_SRC_INCLUDE_DIR ${PROJECT_SOURCE_DIR}/src/include)
# set(SAKURA_TEST_INCLUDE_DIR ${PROJECT_SOURCE_DIR}/test/include) ${SAKURA_TEST_INCLUDE_DIR}
set(SAKURA_THIRD_PARTY_INCLUDE_DIR
        ${PROJECT_SOURCE_DIR}/third_party
        ${PROJECT_SOURCE_DIR}/third_party/fmt/include
)
include_directories(${SAKURA_SRC_INCLUDE_DIR}  ${SAKURA_THIRD_PARTY_INCLUDE_DIR}) # 将指定目录添加到编译器的头文件搜索路径之下

## 2.集成module
add_subdirectory(third_party)
add_subdirectory(src)
# add_subdirectory(test)
add_subdirectory(tools)






