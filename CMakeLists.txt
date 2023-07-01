cmake_minimum_required(VERSION 2.8.3)
project(txt2bag)

## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)

# set(EIGEN3_INCLUDE_DIRS "/usr/include/eigen3/")

find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  roscpp
  rospy
  rosbag
  nav_msgs
  turtlesim
)

find_package(Eigen3 REQUIRED)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES imu_pub
   CATKIN_DEPENDS geometry_msgs roscpp rospy turtlesim message_runtime nav_msgs
#  DEPENDS system_lib
)

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
  ${EIGEN3_INCLUDE_DIRS}
)

add_executable(ins_txt2bag src/ins_txt2bag.cpp)
target_link_libraries(ins_txt2bag ${catkin_LIBRARIES})