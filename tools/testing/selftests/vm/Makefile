# Makefile for vm selftests

CFLAGS = -Wall -I ../../../../usr/include $(EXTRA_CFLAGS)
BINARIES = compaction_test
BINARIES += hugepage-mmap
BINARIES += hugepage-shm
BINARIES += map_hugetlb
BINARIES += mlock2-tests
BINARIES += on-fault-limit
BINARIES += thuge-gen
BINARIES += transhuge-stress
BINARIES += userfaultfd

all: $(BINARIES)
%: %.c
	$(CC) $(CFLAGS) -o $@ $^ -lrt
userfaultfd: userfaultfd.c ../../../../usr/include/linux/kernel.h
	$(CC) $(CFLAGS) -o $@ $< -lpthread

../../../../usr/include/linux/kernel.h:
	make -C ../../../.. headers_install

TEST_PROGS := run_vmtests
TEST_FILES := $(BINARIES)

include ../lib.mk

clean:
	$(RM) $(BINARIES)
