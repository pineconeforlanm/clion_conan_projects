set(PROTO_GENERATE_OUT_PATH "${CMAKE_SOURCE_DIR}/build/x64_Debug/shared")

if (NOT EXISTS ${PROTO_GENERATE_OUT_PATH})
    file(MAKE_DIRECTORY ${PROTO_GENERATE_OUT_PATH})
    message(STATUS "Success create ${PROTO_GENERATE_OUT_PATH}")
else ()
    message(STATUS "${PROTO_GENERATE_OUT_PATH} exists")
endif ()

add_subdirectory(client)
add_subdirectory(service)
add_subdirectory(protos)