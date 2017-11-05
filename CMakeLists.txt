CMAKE_MINIMUM_REQUIRED(VERSION 3.8)
project(tcpdump)

set(CMAKE_VERBOSE_MAKEFILE on)

file(GLOB_RECURSE SOURCE_FILES_DUMMY "*.c" "*.h")

add_executable(zdummy ${SOURCE_FILES_DUMMY})

add_custom_target(tcpdump COMMAND cd ${PROJECT_SOURCE_DIR} && make)

add_definitions(-DHAVE_CONFIG_H)

#[[
building

./configure CFLAGS='-g -O0'
make -j4
]]
