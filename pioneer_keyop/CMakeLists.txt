cmake_minimum_required(VERSION 2.8.3)
project(pioneer_keyop)
find_package(catkin REQUIRED COMPONENTS geometry_msgs std_srvs std_msgs roscpp ecl_exceptions ecl_threads ecl_time kobuki_msgs)

catkin_package(
   INCLUDE_DIRS include
   LIBRARIES kobuki
   CATKIN_DEPENDS geometry_msgs std_srvs std_msgs roscpp ecl_exceptions ecl_threads ecl_time kobuki_msgs
)

include_directories(include ${catkin_INCLUDE_DIRS})

add_executable(pioneer_keyop src/main.cpp src/keyop_core.cpp)
target_link_libraries(pioneer_keyop ${catkin_LIBRARIES})

add_executable(pioneer_gazebo_keyop src/main.cpp src/keyop_core_gazebo.cpp)
target_link_libraries(pioneer_gazebo_keyop ${catkin_LIBRARIES})

add_executable(pioneer_keyop_robot_A src/main.cpp src/keyop_core_robot_A.cpp)
target_link_libraries(pioneer_keyop_robot_A ${catkin_LIBRARIES})

add_executable(pioneer_keyop_robot_B src/main.cpp src/keyop_core_robot_B.cpp)
target_link_libraries(pioneer_keyop_robot_B ${catkin_LIBRARIES})

#add_subdirectory(src)

#install(DIRECTORY include
#  DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
#  FILES_MATCHING PATTERN "*.h*")

#install(DIRECTORY launch
#        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
#)
#install(DIRECTORY param
#        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
#)
