set(FILES
    io.c
    internal.h
    internal.c
    ethash.h
    endian.h
    fnv.h
    data_sizes.h
    sha3.c sha3.h
)

if (MSVC)
    list(APPEND FILES io_win32.c mmap_win32.c)
else()
    list(APPEND FILES io_posix.c)
endif()

add_library(ethash ${FILES})
set_target_properties(ethash PROPERTIES C_STANDARD 99)
