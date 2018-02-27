cmake_minimum_required(VERSION 3.3)

project("DL ISO-8583")


include_directories(
    dl_c_common
    dl_c_iso8583
)

set(dl_c_common_src
    dl_c_common/dl_mem.c
    dl_c_common/dl_output.c
    dl_c_common/dl_str.c
    dl_c_common/dl_time.c
    dl_c_common/dl_timer.c)

add_library(dl_c_common ${dl_c_common_src})

set(dl_c_iso8583_src
    dl_c_iso8583/dl_iso8583.c
    dl_c_iso8583/dl_iso8583_common.c
    dl_c_iso8583/dl_iso8583_defs_1987.c
    dl_c_iso8583/dl_iso8583_defs_1993.c
    dl_c_iso8583/dl_iso8583_fields.c)

add_library(dl_c_iso8583 ${dl_c_iso8583_src})

add_executable(benchmark benchmark.c)
target_link_libraries (benchmark dl_c_iso8583 dl_c_common)

add_executable(demo demo.c)
target_link_libraries (demo dl_c_iso8583 dl_c_common)
