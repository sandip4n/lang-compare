CXX = g++
PROG = hello
OBJS = $(PROG).o

%.o: %.cc
	$(CXX) -c $< -o $@

$(PROG): $(OBJS)
	$(CXX) -o $@ $(OBJS)

clean:
	rm -f $(OBJS)
	rm -f $(NAME)

test:
	perf stat -e cycles,instructions,branches,cache-references $(abspath $(PROG))
