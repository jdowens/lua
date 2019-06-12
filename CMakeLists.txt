project (lua)
cmake_minimum_required(VERSION 3.1)

include_directories(src ${CMAKE_CURRENT_BINARY_DIR})
set_source_files_properties(lapi.c 
                            lcode.c 
                            lctype.c 
                            ldebug.c 
                            ldo.c 
                            ldump.c 
                            lfunc.c 
                            lgc.c 
                            llex.c
                            lmem.c 
                            lobject.c 
                            lopcodes.c 
                            lparser.c 
                            lstate.c 
                            lstring.c 
                            ltable.c
                            ltm.c 
                            lundump.c 
                            lvm.c 
                            lzio.c 
                            lauxlib.c 
                            lbaselib.c 
                            lbitlib.c 
                            lcorolib.c 
                            ldblib.c 
                            liolib.c
                            lmathlib.c 
                            loslib.c 
                            lstrlib.c 
                            ltablib.c 
                            lutf8lib.c 
                            loadlib.c 
                            linit.c 
                            lua.c PROPERTIES LANGUAGE CXX )
set(SRC_CORE lapi.c 
             lcode.c 
             lctype.c 
             ldebug.c 
             ldo.c 
             ldump.c 
             lfunc.c 
             lgc.c 
             llex.c
             lmem.c 
             lobject.c 
             lopcodes.c 
             lparser.c 
             lstate.c 
             lstring.c 
             ltable.c
             ltm.c 
             lundump.c 
             lvm.c 
             lzio.c)
              
set(SRC_LIB  lauxlib.c 
             lbaselib.c 
             lbitlib.c 
             lcorolib.c 
             ldblib.c 
             liolib.c
             lmathlib.c 
             loslib.c 
             lstrlib.c 
             ltablib.c 
             lutf8lib.c 
             loadlib.c 
             linit.c)

set(SRC_LUA lua.c)

add_library(lua-lib ${SRC_CORE} ${SRC_LIB})
set_target_properties(lua-lib PROPERTIES OUTPUT_NAME lua)

add_executable(lua-bin ${SRC_LUA})
set_target_properties(lua-bin PROPERTIES OUTPUT_NAME lua)

target_link_libraries(lua-bin lua-lib)
