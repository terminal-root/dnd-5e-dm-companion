cmake_minimum_required(VERSION 3.24.2)
project(dnd-5e-dm-companion)

set(BINARY_NAME ${PROJECT_NAME}.out)

add_executable(${BINARY_NAME} main.cpp)

include_directories(libs)

# libs

## attached
add_library(base
    libs/base/base.cpp)

target_link_libraries(${BINARY_NAME} base)

## Boost
## Boost
find_package(Boost COMPONENTS filesystem)

include_directories(${Boost_INCLUDE_DIRS})
target_link_libraries(${BINARY_NAME} ${Boost_LIBRARIES})