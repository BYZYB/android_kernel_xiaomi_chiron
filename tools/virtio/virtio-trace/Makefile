CC = gcc
CFLAGS = -Wall -pthread

all: trace-agent

.c.o:
	$(CC) $(CFLAGS) -c $^ -o $@

trace-agent: trace-agent.o trace-agent-ctl.o trace-agent-rw.o
	$(CC) $(CFLAGS) -o $@ $^

clean:
	rm -f *.o trace-agent
