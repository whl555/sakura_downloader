set(MAIN_SOURCES main.cpp)
add_executable(main ${MAIN_SOURCES})

target_link_libraries(main sakura_downloader)
