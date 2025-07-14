find_package(gRPC REQUIRED)

add_executable(grpc_service service.cc)

target_link_libraries(grpc_service grpc::grpc)