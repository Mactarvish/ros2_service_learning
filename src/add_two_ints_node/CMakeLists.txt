cmake_minimum_required(VERSION 3.8)
project(add_two_ints_node)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(std_srvs REQUIRED)
find_package(add_two_ints_srv REQUIRED)

add_executable(${PROJECT_NAME} src/add_two_ints_node.cpp)
ament_target_dependencies(${PROJECT_NAME} rclcpp add_two_ints_srv)

# Install the executable
install(TARGETS
        ${PROJECT_NAME}
        DESTINATION lib/${PROJECT_NAME}
)



ament_package()
