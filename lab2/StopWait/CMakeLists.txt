cmake_minimum_required(VERSION 3.5)
PROJECT(${PROJECT})

SET(CMAKE_C_COMPTLER GCC)
add_definitions(-std=c++11 -Wall -D${CMAKE_PROJECT_NAME})
INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/include)
aux_source_directory(${PROJECT_SOURCE_DIR}/src SRC_LIST)
SET(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
ADD_EXECUTABLE(${CMAKE_PROJECT_NAME} ${SRC_LIST})
FIND_LIBRARY(NETSIM_LIB libnetsim.a ${PROJECT_SOURCE_DIR}/lib)
TARGET_LINK_LIBRARIES(${CMAKE_PROJECT_NAME} ${NETSIM_LIB} -no-pie)