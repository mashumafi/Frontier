add_subdirectory(thirdparty)

SET(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH};${doctest_SOURCE_DIR}/scripts/cmake)

add_subdirectory(adapters)
add_subdirectory(groups)
add_subdirectory(standalones)
add_subdirectory(applications)
