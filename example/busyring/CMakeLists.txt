add_executable(busyring EXCLUDE_FROM_ALL ring.cpp)
add_dependencies(examples busyring)

include(CheckLanguage)
check_language(CUDA)
if(CMAKE_CUDA_COMPILER)
    enable_language(CUDA)
    target_link_libraries(busyring PRIVATE CUDA::cudart)
endif()

target_link_libraries(busyring PRIVATE arbor arborio arborenv arbor-sup)
target_include_directories(busyring PRIVATE "${CMAKE_SOURCE_DIR}/arbor")
