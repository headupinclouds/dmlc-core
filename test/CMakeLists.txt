set(dmlc_tests 
  csv_parser_test.cc
  dataiter_test.cc
  filesys_test.cc
  iostream_test.cc
  libfm_parser_test.cc
  libsvm_parser_test.cc
  recordio_test.cc
  registry_test.cc
  split_read_test.cc
  split_repeat_read_test.cc
  split_test.cc
  stream_read_test.cc
  strtonum_test.cc
  # Exclude intentional failures:
  #logging_test.cc
  #parameter_test.cc
)

foreach(test ${dmlc_tests})
  get_filename_component(test_we ${test} NAME_WE)
  add_executable(${test_we} ${test})
  target_link_libraries(${test_we} PUBLIC dmlc)
  add_test(NAME ${test_we} COMMAND ${test_we})
endforeach()
