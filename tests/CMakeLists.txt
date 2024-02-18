set(TEST_SOURCE main.cpp)
set(TESTS_NAME tests)

include(FetchContent)

FetchContent_Declare(
    googletest-distribution
    GIT_REPOSITORY https://github.com/google/googletest.git
    GIT_TAG v1.14.0
    GIT_SHALLOW TRUE
)

FetchContent_MakeAvailable(googletest-distribution)

add_executable(${TESTS_NAME} ${TEST_SOURCE})



target_link_libraries(${TESTS_NAME} PUBLIC 
    ${LIBRARY_NAME}
    gtest_main
    
    )


add_executable()