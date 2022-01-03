add_executable(drat-trim-bin drat-trim.c)
add_executable(lrat-check-bin lrat-check.c)
add_executable(compress-bin compress.c)
add_executable(decompress-bin decompress.c)

set_target_properties(drat-trim-bin PROPERTIES
        OUTPUT_NAME drat-trim
        RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}")
set_target_properties(lrat-check-bin PROPERTIES
        OUTPUT_NAME lrat-check
        RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}")
set_target_properties(compress-bin PROPERTIES
        OUTPUT_NAME compress
        RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}")
set_target_properties(decompress-bin PROPERTIES
        OUTPUT_NAME decompress
        RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}")

install(TARGETS drat-trim-bin lrat-check-bin compress-bin decompress-bin RUNTIME DESTINATION bin)
