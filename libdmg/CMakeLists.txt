set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -Wextra -Werror \
    -Wno-unused-result -Wno-unused-parameter -Wno-unused-function \
    -Wno-missing-field-initializers -Wno-missing-braces")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -O0")
set(CMAKE_C_STANDARD 11)

set(HEADERS
        include/dmg/dmg.h
        include/dmg/porting.h
        include/dmg/state.h
        include/dmg/cpu.h
        include/dmg/mmu.h
        include/dmg/ppu.h
        )

set(SOURCES
        src/dmg.c
        src/state.c
        src/cpu.c
        src/mmu.c
        src/ppu.c
        )

add_library(libdmg ${HEADERS} ${SOURCES})
target_include_directories(libdmg PUBLIC include)
target_include_directories(libdmg PRIVATE private)