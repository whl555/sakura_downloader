add_library(
    sakura_client 
    OBJECT 
    HttpClient.cpp)

set(ALL_OBJECT_FILES
    ${ALL_OBJECT_FILES} $<TARGET_OBJECTS:sakura_client>
    PARENT_SCOPE)