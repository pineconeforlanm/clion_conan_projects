find_package(gRPC REQUIRED)

add_executable(grpc_service service.cc)

target_include_directories(grpc_service PRIVATE "${CMAKE_SOURCE_DIR}/build/x64_Debug/grpc/protos")
target_link_libraries(grpc_service grpc::grpc proto_hello)