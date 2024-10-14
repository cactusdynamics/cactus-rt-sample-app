cmake_minimum_required(VERSION 3.16)
project(cactus-rt-sample-app)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

include(FetchContent)

SET(CACTUS_RT_ENABLE_TRACING ON)

FetchContent_Declare(
  cactus_rt
  GIT_REPOSITORY https://github.com/cactusdynamics/cactus-rt.git
  GIT_TAG        cmake-update
)
FetchContent_MakeAvailable(cactus_rt)

add_executable(cactus-rt-sample-app
  main.cpp
)

target_link_libraries(cactus-rt-sample-app
  PRIVATE
  cactus_rt
)
