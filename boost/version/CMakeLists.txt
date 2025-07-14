find_package(Boost)

add_executable(boost_version boost_version.cc)

target_link_libraries(boost_version boost::boost)