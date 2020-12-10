add_autoscheduler(NAME liam_test SOURCES AutoSchedule.cpp)

if (BUILD_SHARED_LIBS)
    add_executable(liam_test_cpp test.cpp)
    target_link_libraries(liam_test_cpp PRIVATE Halide::Halide)

    add_test(NAME liam_test_cpp
             COMMAND liam_test_cpp $<TARGET_FILE:Halide_Li2018>)

    set_tests_properties(liam_test_cpp PROPERTIES LABELS Li2018)
endif ()
