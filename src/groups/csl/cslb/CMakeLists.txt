ADD_LIBRARY2(cslb
    FILES
        cslb_bitboard.h2
        cslb_castling.h2
        cslb_direction.h2
        cslb_file.h2
        cslb_move.h2
        cslb_piececolor.h2
        cslb_piecetype.h2
        cslb_position.h2
        cslb_rank.h2
        cslb_session.h2
        cslb_square.h2
        cslb_zobristhash.h2
    EXTRA_ARGS
)

ADD_EXECUTABLE2(cslb_test
    FILES
        cslb_position.t.cpp2
)
TARGET_LINK_LIBRARIES(cslb_test PRIVATE doctest_main cslb)
INCLUDE(doctest)
DOCTEST_DISCOVER_TESTS(cslb_test)
