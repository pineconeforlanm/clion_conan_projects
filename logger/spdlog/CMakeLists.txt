find_package(spdlog)

add_executable(t_spdlog t_spdlog.cc)

target_link_libraries(t_spdlog spdlog::spdlog)