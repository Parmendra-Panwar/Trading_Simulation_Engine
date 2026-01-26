cmake_minimum_required(VERSION 3.16)
project(trading_engine)

set(CMAKE_CXX_STANDARD 17)

include_directories(include)

add_executable(engine
    apps/main.cpp
    src/core/EventLoop.cpp
)

