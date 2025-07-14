find_package(gRPC REQUIRED)

add_executable(grpc_client client.cc)

target_link_libraries(grpc_client grpc::grpc)