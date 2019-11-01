project(lua)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=gnu99 -O2 -Wall -Wextra")

set(CORE_SOURCE_FILES
    lapi.c lcode.c lctype.c ldebug.c
    ldo.c ldump.c lfunc.c lgc.c llex.c lmem.c lobject.c
    lopcodes.c lparser.c lstate.c lstring.c ltable.c ltablib.c ltm.c
    lundump.c lvm.c lzio.c
)

set(LIB_SOURCE_FILES
    lauxlib.c lbaselib.c lbitlib.c lcorolib.c ldblib.c
    linit.c liolib.c lmathlib.c loadlib.c
    loslib.c lstrlib.c ltablib.c lutf8lib.c )

add_library(liblua ${CORE_SOURCE_FILES} ${LIB_SOURCE_FILES})

add_executable(lua lua.c)
target_link_libraries(lua PUBLIC liblua)

add_executable(luac luac.c)
target_link_libraries(luac PUBLIC liblua)
