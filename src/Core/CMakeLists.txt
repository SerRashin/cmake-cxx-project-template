cmake_minimum_required (VERSION 3.8)

set(PROJECT_NAME AppCore)

project (${PROJECT_NAME})

add_library(${PROJECT_NAME} STATIC Config.cpp "Config.h")

## Add libraries
add_subdirectory(Model)
add_subdirectory(Repository)
add_subdirectory(Service)

## include headers
include_directories(Model)
include_directories(Repository)
include_directories(Service)

## Link libraries with project
target_link_libraries(${PROJECT_NAME} PRIVATE Model)
target_link_libraries(${PROJECT_NAME} PRIVATE Repository)
target_link_libraries(${PROJECT_NAME} PRIVATE Service)

set_target_properties(${PROJECT_NAME} PROPERTIES LINKER_LANGUAGE CXX)