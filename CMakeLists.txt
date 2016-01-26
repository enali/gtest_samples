cmake_minimum_required (VERSION 2.8)
project (GTestSample CXX)

option (WITHTEST "compile with test cases" ON)

if (WITHTEST)
  enable_testing()
  find_package (GTest REQUIRED)
  include_directories (${GTEST_INCLUDE_DIRS})
endif (WITHTEST)

add_subdirectory (sample1)
add_subdirectory (sample2)
