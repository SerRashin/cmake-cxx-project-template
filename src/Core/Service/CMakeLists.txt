cmake_minimum_required (VERSION 3.8)

set(PROJECT_NAME Service)

project (${PROJECT_NAME})

file(GLOB LIBRARY_FILES "*.cpp")

add_library(${PROJECT_NAME} STATIC ${LIBRARY_FILES})

target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_SOURCE_DIR}/src/Core)
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_SOURCE_DIR}/src/Core/Model)
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_SOURCE_DIR}/src/Core/Repository)

set_target_properties(${PROJECT_NAME} PROPERTIES LINKER_LANGUAGE CXX)
target_compile_features(${PROJECT_NAME} PUBLIC cxx_std_17)