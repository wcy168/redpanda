rp_test(
  UNIT_TEST
  BINARY_NAME ssx_unit
  SOURCES
    async_transforms.cc
    sformat.cc
    future_util.cc
    thread_worker.cc
    sleep_abortable_test.cc
  DEFINITIONS BOOST_TEST_DYN_LINK
  LIBRARIES v::seastar_testing_main v::ssx
  LABELS ssx
)

rp_test(
  BENCHMARK_TEST
  BINARY_NAME ssx_bench
  SOURCES
    sformat_bench.cc
    thread_worker_bench.cc
  LIBRARIES Seastar::seastar_perf_testing v::ssx
  LABELS ssx
)
