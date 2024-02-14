cmake_minimum_required(VERSION 3.22)

set(PROJECT_NAME cypher)
set(LIBRARY_NAME cypher_libs)

project(
    ${PROJECT_NAME}
    VERSION 1.0.0
    LANGUAGES C CXX
)

set(CMAKE_CXX_STANDARD          17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS        OFF)

option(COMPILE_EXECUTABLE "whether to compile executable" ON)
option(COMPILe_TESTS "whether to compile tests" ON)

set(CMAKE_MODULE_PATH "{PROJECT_SOURCE_DIR}/cmake/")

include(FetchContent)
FetchContent_Declare(
    googletest-distribution
    GIT_REPOSITORY https://github.com/google/googletest
    GIT_TAG v1.14.0
    GIT_SHALLOW TRUE
)

FetchContent_MakeAvailable(googletest-distribution)

FetchContent_Declare(
    googletest-distribution
    GIT_REPOSITORY https://github.com/google/googletest
    GIT_TAG v1.14.0
    GIT_SHALLOW TRUE
)

FetchContent_MakeAvailable(googletest-distribution)



add_subdirectory(external)
add_subdirectory(libs)
add_subdirectory(app)
add_subdirectory(tests)