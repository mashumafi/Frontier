ADD_LIBRARY2(csluci
    FILES
        csluci_program_options.h2
        csluci_input.h2
        csluci_output.h2
    EXTRA_ARGS
)
TARGET_LINK_LIBRARIES(csluci INTERFACE Boost::program_options)

ADD_EXECUTABLE2(csluci_test
    FILES
        csluci_input.t.cpp2
        csluci_output.t.cpp2
        csluci_program_options.t.cpp2
)
TARGET_LINK_LIBRARIES(csluci_test PRIVATE doctest_main csluci)
INCLUDE(doctest)
DOCTEST_DISCOVER_TESTS(csluci_test)
