add_library (sample2 sample2.cc)

if (WITHTEST)
  add_executable (sample2Test sample2_unittest.cc)
  target_link_libraries (sample2Test sample2 ${GTEST_BOTH_LIBRARIES} pthread)
  add_test (NAME sample2_test COMMAND sample2Test)
endif (WITHTEST)
