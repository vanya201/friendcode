cmake_minimum_required(VERSION 3.13 FATAL_ERROR)

set(PROJECT_NAME Falos)
project(${PROJECT_NAME})

add_executable(${PROJECT_NAME} 
    main.cpp
   )

set_property(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR} PROPERTY VS_STARTUP_PROJECT ${PROJECT_NAME})

target_compile_features(${PROJECT_NAME} PUBLIC cxx_std_17)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_INSTALL OFF CACHE BOOL "" FORCE)

add_subdirectory(libs/glfw)
target_link_libraries(${PROJECT_NAME} glfw)
set_target_properties(${PROJECT_NAME} PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin/)

