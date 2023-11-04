ADD_LIBRARY2(cslt
    FILES
        cslt_evaluate.h2
        cslt_fendecoder.h2
        cslt_fenencoder.h2
        cslt_pgndecoder.h2
        cslt_pgnencoder.h2
    EXTRA_ARGS
)
TARGET_LINK_LIBRARIES(cslt INTERFACE cslb)
