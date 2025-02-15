cmake_minimum_required(VERSION 3.27)
project(logger VERSION 1.0.0.0 LANGUAGES C CXX)

# find_package(fmt CONFIG REQUIRED)
include(FetchContent)

FetchContent_Declare(
  fmt
  GIT_REPOSITORY https://github.com/fmtlib/fmt
  GIT_TAG        11.1.3
  GIT_SHALLOW    TRUE
  GIT_PROGRESS   TRUE)
message(STATUS "Using fmt via FetchContent")
FetchContent_MakeAvailable(fmt)

add_library(logger src/logger.cpp)

target_link_libraries(logger fmt::fmt)

target_include_directories(logger PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/src)

