cmake_minimum_required(VERSION 3.5)

project(rasberry_coordination)

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(sensor_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(std_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(rasberry_coordination
  "msg/AgentRegistration.msg"
  "msg/AgentRegistrationList.msg"
  "msg/AgentState.msg"
  "msg/AgentStateList.msg"
  "msg/FullLocation.msg"
  "msg/Interruption.msg"
  "msg/KeyValuePair.msg"
  "msg/MarkerDetails.msg"
  "msg/Module.msg"
  "msg/NewAgentConfig.msg"
  "msg/NewAgentConfigSetup.msg"
  "msg/ServiceQuery.msg"
  "msg/ServiceResponse.msg"
  "msg/TaskDetails.msg"
  "msg/TasksDetails.msg"
  "msg/TopoLocation.msg"
  DEPENDENCIES builtin_interfaces sensor_msgs geometry_msgs std_msgs
)

ament_package()
