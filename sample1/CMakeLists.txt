add_library (sample1 sample1.cc)

if (WITHTEST) 
  add_executable (sample1Test sample1_unittest.cc)
  target_link_libraries (sample1Test sample1 ${GTEST_BOTH_LIBRARIES} pthread)
  add_test (NAME sample1_test COMMAND sample1Test)
endif (WITHTEST)
