cmake_minimum_required(VERSION 3.17)
project(itog1)

set(CMAKE_CXX_STANDARD 17)

set(JSON_BuildTests OFF CACHE INTERNAL "")

add_subdirectory(nlohmann_json)

add_executable(itog1 src/main.cpp src/ConverterJSON.cpp include/ConverterJSON.h src/InvertedIndex.cpp include/InvertedIndex.h src/SearchServer.cpp include/SearchServer.h)

target_link_libraries(itog1 PRIVATE nlohmann_json::nlohmann_json)
target_link_options(itog1 PRIVATE -static-libgcc -static-libstdc++)
