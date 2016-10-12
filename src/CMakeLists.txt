
project(lua)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=gnu99 -O2 -Wall -Wextra")

set(SOURCE_FILES
        lapi.c lauxlib.c lbaselib.c lbitlib.c lcode.c lcorolib.c lctype.c ldblib.c ldebug.c
        ldo.c ldump.c lfunc.c lgc.c linit.c liolib.c llex.c lmathlib.c lmem.c loadlib.c lobject.c
        lopcodes.c loslib.c lparser.c lstate.c lstring.c lstrlib.c ltable.c ltablib.c ltm.c
        lundump.c lutf8lib.c lvm.c lzio.c
        )

add_executable(lua lua.c ${SOURCE_FILES})
target_link_libraries(lua m)

add_executable(luac luac.c ${SOURCE_FILES})
target_link_libraries(luac m)
