include(FetchContent)

FetchContent_Declare(
    doctest
    GIT_REPOSITORY https://github.com/doctest/doctest.git
    GIT_TAG        v2.4.11
)

FetchContent_MakeAvailable(doctest)

#SET(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH};${doctest_SOURCE_DIR}/scripts/cmake)
#INCLUDE(doctest)
