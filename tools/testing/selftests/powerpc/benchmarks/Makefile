TEST_PROGS := gettimeofday

all: $(TEST_PROGS)

$(TEST_PROGS): ../harness.c

include ../../lib.mk

clean:
	rm -f $(TEST_PROGS) *.o
