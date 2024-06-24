set (GCH_SMALL_VECTOR_SOURCE_INCLUDE_DIR ${CMAKE_CURRENT_LIST_DIR}/include CACHE INTERNAL "")

add_library (small_vector INTERFACE)

target_sources (
  small_vector
  INTERFACE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}/include/gch/small_vector.hpp>
)

target_include_directories (
  small_vector
  INTERFACE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}/include>
)

target_include_directories (
  small_vector
  SYSTEM INTERFACE
    $<INSTALL_INTERFACE:$<INSTALL_PREFIX>/${GCH_SMALL_VECTOR_INSTALL_INCLUDE_DIR}>
)

set_target_properties (
  small_vector
  PROPERTIES
  PUBLIC_HEADER
    include/gch/small_vector.hpp
)

target_sources (
  small_vector
  INTERFACE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}/support/visualstudio/small_vector.natvis>
    $<INSTALL_INTERFACE:$<INSTALL_PREFIX>/${GCH_SMALL_VECTOR_INSTALL_SUPPORT_DIR}/visualstudio/small_vector.natvis>
)

add_library (gch::small_vector ALIAS small_vector)
