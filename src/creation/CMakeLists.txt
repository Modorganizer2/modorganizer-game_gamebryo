cmake_minimum_required(VERSION 3.16)

project(game_creation)
set(project_type lib)
set(enable_warnings OFF)
set(create_translations OFF)

# appveyor does not build modorganizer in its standard location, so use
# DEPENDENCIES_DIR to find cmake_common
if(DEFINED DEPENDENCIES_DIR)
	include(${DEPENDENCIES_DIR}/modorganizer_super/cmake_common/project.cmake)
	include(${DEPENDENCIES_DIR}/modorganizer_super/cmake_common/src.cmake)
else()
	include(../../../cmake_common/project.cmake)
	include(../../../cmake_common/src.cmake)
endif()

requires_project(game_gamebryo game_features)
