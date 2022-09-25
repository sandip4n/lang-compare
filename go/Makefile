PROG = hello

build:
	go build $(PROG).go

clean:
	rm -f $(PROG)

test:
	perf stat -e cycles,instructions,branches,cache-references $(abspath $(PROG))
