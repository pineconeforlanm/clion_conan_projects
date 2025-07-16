find_package(gRPC REQUIRED)

add_executable(grpc_client client.cc)

target_include_directories(grpc_client PRIVATE "${CMAKE_SOURCE_DIR}/build/x64_Debug/grpc/protos")
target_link_libraries(grpc_client grpc::grpc proto_hello)