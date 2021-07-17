cmake_minimum_required(VERSION 3.14)
project(apollo C)

set(CMAKE_C_STANDARD 99)

add_library(apollo SHARED apolloclient.c global.c)
target_link_libraries(apollo curl json-c)

file(GLOB APOLLO_HEAD_FILES "${CMAKE_CURRENT_SOURCE_DIR}/*.h")
install(FILES ${APOLLO_HEAD_FILES} DESTINATION include/apollo)
install(TARGETS apollo LIBRARY DESTINATION lib)