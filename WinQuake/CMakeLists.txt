cmake_minimum_required(VERSION 3.3.2)
project(GLQuake)

enable_language(C ASM)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -DGLQUAKE")
set(CMAKE_C_FLAGS_DEBUG "${CMAKE_C_FLAGS_DEBUG} -Wall -g3 -ggdb")
set(CMAKE_C_FLAGS_RELEASE "${CMAKE_C_FLAGS_RELEASE} -Wall -march=native")

set(CMAKE_ASM_FLAGS         "${CMAKE_ASM_FLAGS} -DGLQUAKE -x assembler-with-cpp")
set(CMAKE_ASM_FLAGS_DEBUG   "${CMAKE_ASM_FLAGS_DEBUG} -Wall -g3 -ggdb -DGLQUAKE -x assembler-with-cpp")
set(CMAKE_ASM_FLAGS_RELEASE "${CMAKE_ASM_FLAGS_RELEASE} -DGLQUAKE -x assembler-with-cpp")

set(SOURCE_FILES
    adivtab.h
    anorm_dots.h
    anorms.h
    asm_i386.h
    block16.h
    block8.h
    bspfile.h
    cd_linux.c
    cdaudio.h
    chase.c
    cl_demo.c
    cl_input.c
    cl_main.c
    cl_parse.c
    cl_tent.c
    client.h
    cmd.c
    cmd.h
    common.c
    common.h
    console.c
    console.h
    crc.c
    crc.h
    cvar.c
    cvar.h
    draw.h
    gl_draw.c
    gl_mesh.c
    gl_model.c
    gl_model.h
    gl_refrag.c
    gl_rlight.c
    gl_rmain.c
    gl_rmisc.c
    gl_rsurf.c
    gl_screen.c
    gl_test.c
    gl_vidlinuxglx.c
    gl_warp.c
    gl_warp_sin.h
    glquake.h
    host.c
    host_cmd.c
    input.h
    keys.c
    keys.h
    math.s
    mathlib.c
    mathlib.h
    menu.c
    menu.h
    modelgen.h
    net.h
    net_bsd.c
    net_dgrm.c
    net_dgrm.h
    net_ipx.h
    net_loop.c
    net_loop.h
    net_main.c
    net_udp.c
    net_udp.h
    net_vcr.c
    net_vcr.h
    pr_cmds.c
    pr_comp.h
    pr_edict.c
    pr_exec.c
    progdefs.h
    progs.h
    protocol.h
    quakeasm.h
    quakedef.h
    r_part.c
    render.h
    resource.h
    sbar.c
    sbar.h
    screen.h
    server.h
    snd_dma.c
    snd_linux.c
    snd_mem.c
    snd_mix.c
    sound.h
    spritegn.h
    sv_main.c
    sv_move.c
    sv_phys.c
    sv_user.c
    sys.h
    sys_linux.c
    vgamodes.h
    vid.h
    view.c
    view.h
    wad.c
    wad.h
    world.c
    world.h
    zone.c
    zone.h)

add_executable(GLQuake ${SOURCE_FILES})
target_link_libraries(GLQuake -lGL -lX11 -lXext -ldl -lXxf86dga -lXxf86vm -lm)
