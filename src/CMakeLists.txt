add_subdirectory(download_helper)
add_subdirectory(http_client)

add_library(sakura_downloader STATIC ${ALL_OBJECT_FILES})

set(SAKURA_LIBS
    sakura_download_helper
    sakura_client
        )
find_package(CURL)
set(SAKURA_THIRDPARTY_LIBS
        fmt
        curl
        )
target_link_libraries(sakura_downloader ${SAKURA_LIBS} ${SAKURA_THIRDPARTY_LIBS}) # 当前目录 + 第三方库
target_include_directories(
        sakura_downloader PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
        $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>) # 当前include + cmake include目录

