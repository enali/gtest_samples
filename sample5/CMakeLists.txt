project (Sample5)

include_directories (${Sample1_SOURCE_DIR} ${Sample3_SOURCE_DIR})

set (EXTRA_LIBS ${EXTRA_LIBS} sample1)

sample (FALSE 5)
