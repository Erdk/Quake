#
# Quake Makefile for Linux 2.0
#
# Aug '98 by Zoid <zoid@idsoftware.com>
#
# ELF only
#

BASEVERSION=1.09
VERSION=$(BASEVERSION)

CC=gcc

ARCH=.x86_64

MOUNT_DIR=$(shell pwd)

BUILD_DEBUG_DIR=debug$(ARCH)
BUILD_RELEASE_DIR=release$(ARCH)

BASE_CFLAGS=-Dstricmp=strcasecmp
RELEASE_CFLAGS=$(BASE_CFLAGS) -march=native -O2 -ffast-math -funroll-loops \
	-fomit-frame-pointer -fexpensive-optimizations
DEBUG_CFLAGS=$(BASE_CFLAGS) -g3 -ggdb

GLCFLAGS=-DGLQUAKE
GLLDFLAGS=-lGL -lX11 -lXext -ldl -lXxf86dga -lXxf86vm -lm

DO_GL_CC=$(CC) $(CFLAGS) $(GLCFLAGS) -o $@ -c $<
DO_GL_DEBUG_CC=$(CC) $(DEBUG_CFLAGS) $(GLCFLAGS) -o $@ -c $<
DO_GL_AS=$(CC) $(CFLAGS) $(GLCFLAGS) -x assembler-with-cpp -o $@ -c $<

#############################################################################
# SETUP AND BUILD
#############################################################################

TARGETS=$(BUILDDIR)/bin/glquake.glx

build_debug:
	@-mkdir $(BUILD_DEBUG_DIR) \
		$(BUILD_DEBUG_DIR)/bin \
		$(BUILD_DEBUG_DIR)/glquake
	$(MAKE) targets BUILDDIR=$(BUILD_DEBUG_DIR) CFLAGS="$(DEBUG_CFLAGS)"

build_release:
	@-mkdir $(BUILD_RELEASE_DIR) \
		$(BUILD_RELEASE_DIR)/bin \ 
		$(BUILD_RELEASE_DIR)/glquake 
	$(MAKE) targets BUILDDIR=$(BUILD_RELEASE_DIR) CFLAGS="$(RELEASE_CFLAGS)"

all: build_debug build_release

targets: $(TARGETS)

#############################################################################
# GLQuake
#############################################################################

GLQUAKE_OBJS= \
	$(BUILDDIR)/glquake/chase.o \
	$(BUILDDIR)/glquake/cl_demo.o \
	$(BUILDDIR)/glquake/cl_input.o \
	$(BUILDDIR)/glquake/cl_main.o \
	$(BUILDDIR)/glquake/cl_parse.o \
	$(BUILDDIR)/glquake/cl_tent.o \
	$(BUILDDIR)/glquake/cmd.o \
	$(BUILDDIR)/glquake/common.o \
	$(BUILDDIR)/glquake/console.o \
	$(BUILDDIR)/glquake/crc.o \
	$(BUILDDIR)/glquake/cvar.o \
	\
	$(BUILDDIR)/glquake/gl_draw.o \
	$(BUILDDIR)/glquake/gl_mesh.o \
	$(BUILDDIR)/glquake/gl_model.o \
	$(BUILDDIR)/glquake/gl_refrag.o \
	$(BUILDDIR)/glquake/gl_rlight.o \
	$(BUILDDIR)/glquake/gl_rmain.o \
	$(BUILDDIR)/glquake/gl_rmisc.o \
	$(BUILDDIR)/glquake/gl_rsurf.o \
	$(BUILDDIR)/glquake/gl_screen.o \
	$(BUILDDIR)/glquake/gl_test.o \
	$(BUILDDIR)/glquake/gl_vidlinuxglx.o \
	$(BUILDDIR)/glquake/gl_warp.o \
	\
	$(BUILDDIR)/glquake/cd_linux.o \
	$(BUILDDIR)/glquake/host.o \
	$(BUILDDIR)/glquake/host_cmd.o \
	$(BUILDDIR)/glquake/keys.o \
	$(BUILDDIR)/glquake/mathlib.o \
	$(BUILDDIR)/glquake/menu.o \
	$(BUILDDIR)/glquake/net_bsd.o \
	$(BUILDDIR)/glquake/net_dgrm.o \
	$(BUILDDIR)/glquake/net_loop.o \
	$(BUILDDIR)/glquake/net_main.o \
	$(BUILDDIR)/glquake/net_udp.o \
	$(BUILDDIR)/glquake/net_vcr.o \
	$(BUILDDIR)/glquake/pr_cmds.o \
	$(BUILDDIR)/glquake/pr_edict.o \
	$(BUILDDIR)/glquake/pr_exec.o \
	$(BUILDDIR)/glquake/r_part.o \
	$(BUILDDIR)/glquake/sbar.o \
	$(BUILDDIR)/glquake/snd_dma.o \
	$(BUILDDIR)/glquake/snd_linux.o \
	$(BUILDDIR)/glquake/snd_mem.o \
	$(BUILDDIR)/glquake/snd_mix.o \
	$(BUILDDIR)/glquake/sv_main.o \
	$(BUILDDIR)/glquake/sv_move.o \
	$(BUILDDIR)/glquake/sv_phys.o \
	$(BUILDDIR)/glquake/sv_user.o \
	$(BUILDDIR)/glquake/sys_linux.o \
	$(BUILDDIR)/glquake/view.o	\
	$(BUILDDIR)/glquake/wad.o \
	$(BUILDDIR)/glquake/world.o \
	$(BUILDDIR)/glquake/zone.o	\
	\
	$(BUILDDIR)/glquake/math.o \
	$(BUILDDIR)/glquake/snd_mixa.o \
	$(BUILDDIR)/glquake/sys_dosa.o \
	$(BUILDDIR)/glquake/worlda.o

$(BUILDDIR)/bin/glquake.glx : $(GLQUAKE_OBJS)
	$(CC) $(CFLAGS) -o $@ $(GLQUAKE_OBJS) $(GLLDFLAGS)

$(BUILDDIR)/glquake/cl_demo.o :      $(MOUNT_DIR)/cl_demo.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/cl_input.o :     $(MOUNT_DIR)/cl_input.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/cl_main.o :      $(MOUNT_DIR)/cl_main.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/cl_parse.o :     $(MOUNT_DIR)/cl_parse.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/cl_tent.o :      $(MOUNT_DIR)/cl_tent.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/chase.o :        $(MOUNT_DIR)/chase.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/cmd.o :          $(MOUNT_DIR)/cmd.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/common.o :       $(MOUNT_DIR)/common.c
	$(DO_GL_DEBUG_CC)

$(BUILDDIR)/glquake/console.o :      $(MOUNT_DIR)/console.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/crc.o :          $(MOUNT_DIR)/crc.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/cvar.o :         $(MOUNT_DIR)/cvar.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/gl_draw.o :      $(MOUNT_DIR)/gl_draw.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/gl_mesh.o :      $(MOUNT_DIR)/gl_mesh.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/gl_model.o :     $(MOUNT_DIR)/gl_model.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/gl_refrag.o :    $(MOUNT_DIR)/gl_refrag.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/gl_rlight.o :    $(MOUNT_DIR)/gl_rlight.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/gl_rmain.o :     $(MOUNT_DIR)/gl_rmain.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/gl_rmisc.o :     $(MOUNT_DIR)/gl_rmisc.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/gl_rsurf.o :     $(MOUNT_DIR)/gl_rsurf.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/gl_screen.o :    $(MOUNT_DIR)/gl_screen.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/gl_test.o :      $(MOUNT_DIR)/gl_test.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/gl_vidlinuxglx.o :  $(MOUNT_DIR)/gl_vidlinuxglx.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/gl_warp.o :      $(MOUNT_DIR)/gl_warp.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/host.o :         $(MOUNT_DIR)/host.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/host_cmd.o :     $(MOUNT_DIR)/host_cmd.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/keys.o :         $(MOUNT_DIR)/keys.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/menu.o :         $(MOUNT_DIR)/menu.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/mathlib.o :      $(MOUNT_DIR)/mathlib.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/net_dgrm.o :     $(MOUNT_DIR)/net_dgrm.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/net_loop.o :     $(MOUNT_DIR)/net_loop.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/net_main.o :     $(MOUNT_DIR)/net_main.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/net_vcr.o :      $(MOUNT_DIR)/net_vcr.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/net_udp.o :      $(MOUNT_DIR)/net_udp.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/net_bsd.o :      $(MOUNT_DIR)/net_bsd.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/pr_cmds.o :      $(MOUNT_DIR)/pr_cmds.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/pr_edict.o :     $(MOUNT_DIR)/pr_edict.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/pr_exec.o :      $(MOUNT_DIR)/pr_exec.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/r_part.o :       $(MOUNT_DIR)/r_part.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/sbar.o :         $(MOUNT_DIR)/sbar.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/sv_main.o :      $(MOUNT_DIR)/sv_main.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/sv_phys.o :      $(MOUNT_DIR)/sv_phys.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/sv_move.o :      $(MOUNT_DIR)/sv_move.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/sv_user.o :      $(MOUNT_DIR)/sv_user.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/zone.o	:        $(MOUNT_DIR)/zone.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/view.o	:        $(MOUNT_DIR)/view.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/wad.o :          $(MOUNT_DIR)/wad.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/world.o :        $(MOUNT_DIR)/world.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/cd_linux.o :     $(MOUNT_DIR)/cd_linux.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/sys_linux.o :    $(MOUNT_DIR)/sys_linux.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/snd_dma.o :      $(MOUNT_DIR)/snd_dma.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/snd_mem.o :      $(MOUNT_DIR)/snd_mem.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/snd_mix.o :      $(MOUNT_DIR)/snd_mix.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/snd_linux.o :    $(MOUNT_DIR)/snd_linux.c
	$(DO_GL_CC)

$(BUILDDIR)/glquake/math.o :         $(MOUNT_DIR)/math.s
	$(DO_GL_AS)

$(BUILDDIR)/glquake/worlda.o :       $(MOUNT_DIR)/worlda.s
	$(DO_GL_AS)

$(BUILDDIR)/glquake/snd_mixa.o :     $(MOUNT_DIR)/snd_mixa.s
	$(DO_GL_AS)

$(BUILDDIR)/glquake/sys_dosa.o :     $(MOUNT_DIR)/sys_dosa.s
	$(DO_GL_AS)

#############################################################################
# MISC
#############################################################################

clean: clean-debug clean-release

clean-debug:
	$(MAKE) clean2 BUILDDIR=$(BUILD_DEBUG_DIR) CFLAGS="$(DEBUG_CFLAGS)"

clean-release:
	$(MAKE) clean2 BUILDDIR=$(BUILD_RELEASE_DIR) CFLAGS="$(DEBUG_CFLAGS)"

clean2:
	-rm -f $(GLQUAKE_OBJS)

