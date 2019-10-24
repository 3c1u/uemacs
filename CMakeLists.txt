cmake_minimum_required(VERSION 2.8)

project(uemacs)

add_executable(uemacs 
    ansi.c basic.c bind.c buffer.c crypt.c display.c eval.c exec.c
	file.c fileio.c ibmpc.c input.c isearch.c line.c lock.c main.c
	pklock.c posix.c random.c region.c search.c spawn.c tcap.c
	termio.c vmsvt.c vt52.c window.c word.c names.c globals.c version.c
    usage.c wrapper.c utf8.c util.c
)

add_definitions(
    -DAUTOCONF -DPOSIX -DSYSV -D_DARWIN_C_SOURCE -D_BSD_SOURCE -D_SVID_SOURCE -D_XOPEN_SOURCE=600
)

# find_package(curses REQUIRED)

target_link_libraries(uemacs
    curses
)