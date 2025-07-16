find_package(Protobuf REQUIRED)
find_package(gRPC CONFIG REQUIRED)

set(PROTO_LIB_NAME proto_hello)

file(GLOB_RECURSE PROTO_SOURCE_FILES "*.proto")

add_library(${PROTO_LIB_NAME} ${PROTO_SOURCE_FILES})
target_link_libraries(${PROTO_LIB_NAME} PUBLIC gRPC::grpc++)

protobuf_generate(TARGET ${PROTO_LIB_NAME} PROTOC_OUT_DIR "${PROTO_GENERATE_OUT_PATH}")
protobuf_generate(
        TARGET ${PROTO_LIB_NAME}
        LANGUAGE grpc
        PROTOC_OUT_DIR "${PROTO_GENERATE_OUT_PATH}"
        PLUGIN protoc-gen-grpc=$<TARGET_FILE:gRPC::grpc_cpp_plugin>
        PLUGIN_OPTIONS generate_mock_code=true
        GENERATE_EXTENSIONS .grpc.pb.h .grpc.pb.cc
)