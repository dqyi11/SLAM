cmake_minimum_required(VERSION 2.8)
project(slam_navigation)

find_package(catkin REQUIRED COMPONENTS
             roscpp
             sensor_msgs
             geometry_msgs
             tf
             move_base_msgs
             actionlib
            )

catkin_package(
  CATKIN_DEPENDS message_runtime
)

add_executable(slam_navigation src/turtlebot_navigator.cpp
              )

target_link_libraries(slam_navigation ${catkin_LIBRARIES}
                     )
