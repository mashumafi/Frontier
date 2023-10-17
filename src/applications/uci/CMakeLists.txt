ADD_EXECUTABLE2(uci
    FILES
        uci.m.cpp2
    EXTRA_ARGS -in
)
TARGET_LINK_LIBRARIES(uci PRIVATE cslb cslt)
