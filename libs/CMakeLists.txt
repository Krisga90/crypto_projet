set(LIBRARY_SOURCES "src/my_lib.cpp")
set(LIBRARY_HEADERS "include/my_lib.hpp")
set(LIBRARY_INCLUDES "./include")


add_library(${LIBRARY_NAME} STATIC
    ${LIBRARY_SOURCES}
    ${LIBRARY_HEADERS})
    
target_include_directories( ${LIBRARY_NAME} PUBLIC
    ${LIBRARY_INCLUDES})

target_link_libraries(${LIBRARY_NAME} PUBLIC
    cxxopts::cxxopts
    )