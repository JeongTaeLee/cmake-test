cmake_minimum_required(VERSION 3.25)

project(cmake-test LANGUAGES CXX)

add_subdirectory("test-library")
add_subdirectory("test-application")

add_dependencies("test-application" "test-library")