add_executable(busyring EXCLUDE_FROM_ALL ring.cpp)
add_dependencies(examples busyring)

target_link_libraries(busyring PRIVATE arbor arborio arborenv arbor-sup)
target_include_directories(busyring PRIVATE "${CMAKE_SOURCE_DIR}/arbor")
