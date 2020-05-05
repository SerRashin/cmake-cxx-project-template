cmake_minimum_required (VERSION 3.8)

set(PROJECT_NAME Application)


project(${PROJECT_NAME})

## executable file
add_executable(${PROJECT_NAME} main.cpp)

# add subproject
add_subdirectory(Core)

## include subproect headers
include_directories(Core)

## link project with libraries
target_link_libraries(${PROJECT_NAME} PRIVATE AppCore)
