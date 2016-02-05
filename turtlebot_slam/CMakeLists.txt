cmake_minimum_required(VERSION 2.8)
project(turtlebot_slam)

find_package(catkin REQUIRED roscpp)

catkin_package(
  CATKIN_DEPENDS
)

add_executable(turtlebot_exploration src/wavefront_frontier_detection.cpp
                                     src/turtlebot_mapping.cpp
              )

target_link_libraries(turtlebot_exploration ${catkin_LIBRARIES} 
                     )
