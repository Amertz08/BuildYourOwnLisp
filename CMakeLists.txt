cmake_minimum_required(VERSION 3.10)
project(lisp C)

set(CMAKE_C_STANDARD 99)

set(LIBS edit mpc)
set(MPC_DIR ../mpc)

# Build MPC lib
set(MPC_SRC ${MPC_DIR}/mpc.h ${MPC_DIR}/mpc.c)
add_library(mpc ${MPC_SRC})
include_directories(${MPC_DIR})

add_executable(lisp main.c)
target_link_libraries(lisp ${LIBS})
