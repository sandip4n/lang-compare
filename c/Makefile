CC = gcc
PROG = hello
OBJS = $(PROG).o

%.o: %.c
	$(CC) -c $< -o $@

$(PROG): $(OBJS)
	$(CC) -o $@ $(OBJS)

clean:
	rm -f $(OBJS)
	rm -f $(PROG)

test:
	perf stat -e cycles,instructions,branches,cache-references $(abspath $(PROG))
