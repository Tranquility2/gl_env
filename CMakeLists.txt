cmake_minimum_required (VERSION 3.11)
cmake_policy(SET CMP0048 NEW)
project(gl_env VERSION 0.0.1 LANGUAGES CXX)

add_executable(gl_env main.cpp)

include(FetchContent)
FetchContent_Declare(
  glfw
  GIT_REPOSITORY https://github.com/glfw/glfw.git
  GIT_TAG        master
)
FetchContent_Declare(
  glew
  GIT_REPOSITORY https://github.com/Perlmint/glew-cmake
  GIT_TAG        master
)

# Disable GLFW documentation build
option (GLFW_BUILD_DOCS "Build the GLFW documentation" ON)
set(GLFW_BUILD_DOCS OFF)

FetchContent_MakeAvailable(glew glfw)

# add_library(glew STATIC IMPORTED)
# set_target_properties(glew PROPERTIES
    # IMPORTED_LOCATION_RELEASE glew.lib
    # IMPORTED_LOCATION_DEBUG   glewd.lib
# )
# link_directories(${CMAKE_BINARY_DIR}/lib)
# target_link_libraries(gl_env glew)

add_definitions(-DGLEW_STATIC)
target_link_libraries(gl_env PRIVATE libglew_static glfw)

message("PROJECT_NAME              ${PROJECT_NAME}")
message("PROJECT_SOURCE_DIR        ${PROJECT_SOURCE_DIR}")
message("PROJECT_BINARY_DIR        ${PROJECT_BINARY_DIR}")
message("CMAKE_SOURCE_DIR          ${CMAKE_SOURCE_DIR}")
message("CMAKE_CURRENT_SOURCE_DIR  ${CMAKE_CURRENT_SOURCE_DIR}")
message("CMAKE_BINARY_DIR          ${CMAKE_BINARY_DIR}")
message("CMAKE_CURRENT_BINARY_DIR  ${CMAKE_CURRENT_BINARY_DIR}")
message("CMAKE_INSTALL_PREFIX      ${CMAKE_INSTALL_PREFIX}")