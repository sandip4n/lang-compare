PROG = hello

build:
	rustc -o $(PROG) $(PROG).rs

clean:
	rm -f $(PROG)

test:
	perf stat -e cycles,instructions,branches,cache-references $(abspath $(PROG))
