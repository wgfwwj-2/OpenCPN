cmake_minimum_required(VERSION 3.1.0)

if (TARGET ssl::sha1)
    return ()
endif ()

add_library(SHA1 STATIC include/ssl/sha1.h src/sha1.c)
set_property(TARGET SHA1 PROPERTY COMPILE_FLAGS "${OBJ_VISIBILITY}")
target_include_directories(SHA1 PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)
add_library(ssl::sha1 ALIAS SHA1)
