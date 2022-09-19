cmake_minimum_required(VERSION 3.24)
# reminder: change cmake_c_project_template
project(
  cmake_c_project_template
  VERSION 0.1.0
  LANGUAGES C)
# C99 ISO standard
set(CMAKE_C_STANDARD 99)
# Require standard
set(CMAKE_C_STANDARD_REQUIRED ON)
# set release build
set(CMAKE_BUILD_TYPE Release)
# create build dir
file(MAKE_DIRECTORY "${PROJECT_SOURCE_DIR}/build")
# generate compile_commands.json
set(CMAKE_EXPORT_COMPILE_COMMANDS 1)
# create executable from src/
include_directories("${PROJECT_SOURCE_DIR}/include")
file(GLOB_RECURSE "${PROJECT_NAME}_SOURCES" "${PROJECT_SOURCE_DIR}/src/*.c")
add_executable(${PROJECT_NAME} ${${PROJECT_NAME}_SOURCES})
