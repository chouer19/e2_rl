cmake_minimum_required(VERSION 2.8.3)
project(plugins)
add_definitions(${Qt5Core_DEFINITIONS})
set (CMAKE_AUTOMOC ON)

find_package(gazebo)
find_package(catkin REQUIRED COMPONENTS roscpp rospy std_msgs nav_msgs geometry_msgs genmsg prius_msgs)
generate_messages(DEPENDENCIES std_msgs)
catkin_package()
include_directories(include ${catkin_INCLUDE_DIRS})

include_directories(
  ${GAZEBO_INCLUDE_DIRS}
  ${Qt5Core_INCLUDE_DIRS}
)
link_directories(${GAZEBO_LIBRARY_DIRS})
list(APPEND CMAKE_CXX_FLAGS "${GAZEBO_CXX_FLAGS}")

set (plugins
  ChongPriusPlugin
)

add_executable(priusDriver src/priusDriver.cpp src/priusDriver.h)
target_link_libraries(priusDriver ${catkin_LIBRARIES} ${GAZEBO_LIBRARIES})
add_dependencies(priusDriver plugins_generate_messages_cpp)
