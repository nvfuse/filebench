SUBDIRS = workloads cvars

# we depend on this lex & yacc generated file
BUILT_SOURCES = parser_gram.h

bin_PROGRAMS = filebench
filebench_SOURCES = eventgen.c fb_avl.c fb_localfs.c \
		    fb_random.c fileset.c flowop.c flowop_library.c \
		    gamma_dist.c ipc.c misc.c multi_client_sync.c \
		    parser_gram.y parser_lex.l procflow.c stats.c \
		    threadflow.c utils.c vars.c ioprio.c \
		    eventgen.h  fb_random.h  fileset.h  fsplug.h \
		    ipc.h   multi_client_sync.h  parsertypes.h  stats.h \
		    utils.h config.h fb_avl.h filebench.h flowop.h gamma_dist.h \
		    misc.h procflow.h threadflow.h vars.h ioprio.h flag.h \
		    fbtime.c fbtime.h \
		    fb_cvar.c fb_cvar.h aslr.c aslr.h \
		    cvars/mtwist/mtwist.c cvars/mtwist/mtwist.h

EXTRA_DIST = LICENSE

ACLOCAL_AMFLAGS = -I m4
AM_YFLAGS = -d
#AM_LDFLAGS = 
if GCC_USED
NVFUSE_ROOT_DIR = /home/ysoh/nvfuse
SPDK_DIR = /home/ysoh/spdk/build/lib
DPDK_DIR = /home/ysoh/spdk/dpdk-16.11/x86_64-native-linuxapp-gcc/build/lib/
AM_CFLAGS = -g -Wall -Wno-unknown-pragmas -I$(NVFUSE_ROOT_DIR)/include
AM_LDFLAGS = $(NVFUSE_ROOT_DIR)/nvfuse.a $(SPDK_DIR)/libspdk_nvme.a $(SPDK_DIR)/libspdk_env_dpdk.a \
			 $(SPDK_DIR)/libspdk_log.a $(SPDK_DIR)/libspdk_util.a \
			 $(DPDK_DIR)/librte_ring/librte_ring.a $(DPDK_DIR)/librte_mbuf/librte_mbuf.a \
			 $(DPDK_DIR)/librte_eal/linuxapp/eal/librte_eal.a \
			 $(DPDK_DIR)/librte_timer/librte_timer.a \
			 $(DPDK_DIR)/librte_mempool/librte_mempool.a

endif

DEFS = -D_REENTRANT -DYYDEBUG -DYY_NO_INPUT -DFBDATADIR=\"$(datadir)/filebench\" -D_LARGEFILE64_SOURCE -D_GNU_SOURCE
