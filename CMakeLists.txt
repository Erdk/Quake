cmake_minimum_required(VERSION 3.3.2)
project(GLQuake)

find_package(glfw3 REQUIRED)

enable_language(C ASM)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -DGLQUAKE")
set(CMAKE_C_FLAGS_DEBUG "${CMAKE_C_FLAGS_DEBUG} -Wall -g3 -ggdb")
set(CMAKE_C_FLAGS_RELEASE "${CMAKE_C_FLAGS_RELEASE} -Wall -march=native")

set(CMAKE_ASM_FLAGS         "${CMAKE_ASM_FLAGS} -DGLQUAKE -x assembler-with-cpp")
set(CMAKE_ASM_FLAGS_DEBUG   "${CMAKE_ASM_FLAGS_DEBUG} -Wall -g3 -ggdb -DGLQUAKE -x assembler-with-cpp")
set(CMAKE_ASM_FLAGS_RELEASE "${CMAKE_ASM_FLAGS_RELEASE} -DGLQUAKE -x assembler-with-cpp")

set(SOURCE_FILES
    src/adivtab.h
    src/anorm_dots.h
    src/anorms.h
    src/asm_i386.h
    src/block16.h
    src/block8.h
    src/bspfile.h
    src/cd_linux.c
    src/cdaudio.h
    src/chase.c
    src/cl_demo.c
    src/cl_input.c
    src/cl_main.c
    src/cl_parse.c
    src/cl_tent.c
    src/client.h
    src/cmd.c
    src/cmd.h
    src/common.c
    src/common.h
    src/console.c
    src/console.h
    src/crc.c
    src/crc.h
    src/cvar.c
    src/cvar.h
    src/draw.h
    src/gl_draw.c
    src/gl_mesh.c
    src/gl_model.c
    src/gl_model.h
    src/gl_refrag.c
    src/gl_rlight.c
    src/gl_rmain.c
    src/gl_rmisc.c
    src/gl_rsurf.c
    src/gl_screen.c
    src/gl_test.c
    src/gl_vidlinuxglx.c
    src/gl_warp.c
    src/gl_warp_sin.h
    src/glquake.h
    src/host.c
    src/host_cmd.c
    src/input.h
    src/keys.c
    src/keys.h
    src/math.s
    src/mathlib.c
    src/mathlib.h
    src/menu.c
    src/menu.h
    src/modelgen.h
    src/net.h
    src/net_bsd.c
    src/net_dgrm.c
    src/net_dgrm.h
    src/net_ipx.h
    src/net_loop.c
    src/net_loop.h
    src/net_main.c
    src/net_udp.c
    src/net_udp.h
    src/net_vcr.c
    src/net_vcr.h
    src/pr_cmds.c
    src/pr_comp.h
    src/pr_edict.c
    src/pr_exec.c
    src/progdefs.h
    src/progs.h
    src/protocol.h
    src/quakeasm.h
    src/quakedef.h
    src/r_part.c
    src/render.h
    src/resource.h
    src/sbar.c
    src/sbar.h
    src/screen.h
    src/server.h
    src/snd_dma.c
    src/snd_linux.c
    src/snd_mem.c
    src/snd_mix.c
    src/sound.h
    src/spritegn.h
    src/sv_main.c
    src/sv_move.c
    src/sv_phys.c
    src/sv_user.c
    src/sys.h
    src/sys_linux.c
    src/vgamodes.h
    src/vid.h
    src/view.c
    src/view.h
    src/wad.c
    src/wad.h
    src/world.c
    src/world.h
    src/zone.c
    src/zone.h)

add_executable(GLQuake ${SOURCE_FILES})
target_link_libraries(GLQuake glfw -lm -ldl -lGL)
