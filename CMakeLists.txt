cmake_minimum_required(VERSION 2.8)
PROJECT(iit-coman-ros-pkg)

add_custom_target(	remove_old_coman_gazebo ALL
    				COMMAND ${CMAKE_COMMAND} -E remove_directory 
        			"~/.gazebo/models/coman_urdf/")
add_custom_target(	copy_coman_gazebo ALL
    				COMMAND ${CMAKE_COMMAND} -E copy_directory 
        			"${PROJECT_SOURCE_DIR}/coman_gazebo/sdf/" 
        			"~/.gazebo/models/coman_urdf/"
        			DEPENDS remove_old_coman_gazebo)