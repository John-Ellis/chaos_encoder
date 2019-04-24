cmake_minimum_required(VERSION 3.0)

set(CMAKE_CXX_STANDARD 14)

project(chaos_encoder)

# target
set(SOURCE ./src/chaos_encoder.cpp)
add_executable(${PROJECT_NAME} ${SOURCE})