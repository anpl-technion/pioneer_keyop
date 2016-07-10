##############################################################################
# Sources
##############################################################################

file(GLOB SOURCES RELATIVE ${CMAKE_CURRENT_SOURCE_DIR} *.cpp)

##############################################################################
# Targets
##############################################################################

add_executable(pioneer_keyop ${SOURCES})
add_dependencies(pioneer_keyop kobuki_msgs_gencpp)
target_link_libraries(pioneer_keyop ${catkin_LIBRARIES})

install(TARGETS pioneer_keyop
        DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
