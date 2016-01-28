cmake_minimum_required (VERSION 2.8)
project (GTestSample CXX)

set (CMAKE_CXX_FLAGS "-std=c++11 -stdlib=libc++ -Wall")
set (CMAKE_EXE_LINKER_FLAGS "-lc++abi")

include_directories (${PROJECT_SOURCE_DIR}/include)

option (WITHTEST "compile with test cases" ON)

if (WITHTEST)
  enable_testing()
  find_package (GTest REQUIRED)
  include_directories (${GTEST_INCLUDE_DIRS})
  message (STATUS "gtest_both_libraries is ${GTEST_BOTH_LIBRARIES}")
endif (WITHTEST)

# if the sample make library, then the parameter lib is TRUE
macro (sample lib n)
  if (${lib})
    add_library (sample${n} sample${n}.cc)
    set (EXTRA_LIBS ${EXTRA_LIBS} sample${n})
  endif (${lib})
  if (WITHTEST) 
    add_executable (sample${n}Test sample${n}_unittest.cc)
    target_link_libraries (sample${n}Test ${GTEST_BOTH_LIBRARIES} pthread ${EXTRA_LIBS})
    add_test (NAME sample${n}_test COMMAND sample${n}Test)
  endif (WITHTEST)
endmacro (sample)

subdirs (sample1 sample2 sample3 sample4 sample5 sample6)

add_custom_target (check COMMAND ${CMAKE_CTEST_COMMAND} --output-on-failure)
