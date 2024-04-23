add_library(
    sakura_download_helper 
    OBJECT 
    Downloader.cpp)

set(ALL_OBJECT_FILES
    ${ALL_OBJECT_FILES} $<TARGET_OBJECTS:sakura_download_helper>
    PARENT_SCOPE)

