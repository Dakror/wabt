
project(libdwarf)

add_library(${PROJECT_NAME} SHARED IMPORTED GLOBAL)

find_package(ZLIB)

set_target_properties(${PROJECT_NAME} PROPERTIES
  INTERFACE_INCLUDE_DIRECTORIES "${CMAKE_CURRENT_LIST_DIR}/include"
  IMPORTED_LOCATION "${CMAKE_CURRENT_LIST_DIR}/lib/libdwarf.so"
)

target_link_libraries(libdwarf INTERFACE ZLIB::ZLIB)