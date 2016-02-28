cmake_minimum_required(VERSION 2.8)
project(turtlebot_graphslam)

find_package(catkin REQUIRED roscpp
                             cmake_modules
             )

catkin_package(
  CATKIN_DEPENDS
)


find_package(Eigen REQUIRED)
include_directories(${EIGEN_INCLUDE_DIRS})
add_definitions(${EIGEN_DEFINITIONS})

find_path(CSPARSE_INCLUDE_DIR
          cs.h
         HINTS $ENV{CSPARSE}/include /usr/include/suitesparse
         )
include_directories(${CSPARSE_INCLUDE_DIR})
message("CSPARSE ${CSPARSE_INCLUDE_DIR}")
#set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
#set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib)
include_directories(${PROJECT_SOURCE_DIR}/include)

add_library(graph src/graph.cpp)
#add_library(scanmatcher src/scanmatcher.cpp)

#target_link_libraries(scanmatcher "${PROJECT_SOURCE_DIR}/lib64/libcsm.so")

#add_executable(${PROJECT_NAME} src/graphslam.cpp
#              )
#add_executable(sm_node src/sm_node.cpp
#              )
#target_link_libraries(${PROJECT_NAME} graph)
#target_link_libraries(sm_node scanmatcher)
#target_link_libraries(graph g2o_core g2o_stuff g2o_types_slam2d g2o_solver_cholmod g2o_solver_pcg g2o_solver_csparse cxsparse g2o_incremental g2o_csparse_extension scanmatcher csparse)
