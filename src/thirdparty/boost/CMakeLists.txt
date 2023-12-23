FUNCTION(FETCH_BOOST)
    CMAKE_PARSE_ARGUMENTS(BOOST_ARGS "" "VERSION" "LIBS" ${ARGN})

    INCLUDE(FetchContent)

    FOREACH(LIB IN LISTS BOOST_ARGS_LIBS)
        MESSAGE("Fetching Boost::${LIB}")
        FetchContent_Declare(
            ${LIB}
            GIT_REPOSITORY https://github.com/boostorg/${LIB}.git
            GIT_TAG        boost-${BOOST_ARGS_VERSION}
        )

        FetchContent_MakeAvailable(${LIB})
    ENDFOREACH()

ENDFUNCTION()

FETCH_BOOST(
    LIBS
        any
        assert
        bind
        concept_check
        config
        container
        container_hash
        conversion
        core
        describe
        detail
        function
        function_types
        functional
        fusion
        integer
        intrusive
        io
        iterator
        lexical_cast
        move
        mp11
        mpl
        numeric_conversion
        optional
        predef
        preprocessor
        program_options
        smart_ptr
        static_assert
        throw_exception
        tokenizer
        tuple
        type_index
        type_traits
        typeof
        utility

    VERSION 1.84.0
)
