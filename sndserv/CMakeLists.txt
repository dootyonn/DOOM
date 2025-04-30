cmake_minimum_required(VERSION 3.28)

add_executable(sndserv
    linux.c
    sounds.c
    soundsrv.c
    wadread.c
)

target_include_directories(sndserv
PRIVATE
    .
)

target_compile_features(sndserv
PRIVATE
    c_std_99
)

target_compile_definitions(sndserv
PRIVATE
    NORMALUNIX=1
    LINUX=1
)

target_compile_options(sndserv
PRIVATE
    -g -Wno-all -std=gnu99
)

target_link_libraries(sndserv
PRIVATE
    m
)