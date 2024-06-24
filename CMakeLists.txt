cmake_minimum_required (VERSION 3.15)

project (
  small_vector
  VERSION
    0.9.2
  LANGUAGES
    CXX
)

string (COMPARE EQUAL "${CMAKE_CURRENT_SOURCE_DIR}" "${CMAKE_SOURCE_DIR}" _IS_PROJECT_ROOT)

add_subdirectory (source)
