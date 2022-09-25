# lang-compare
The idea is to provide a a simple, objective way to compare popular systems
programming languages starting with a basic `Hello World` program. This relies
on the availability of `perf` and certain hardware performance monitoring
events. No special optimization flags are passed to the toolchain components
for building the binaries.

This test should work on any platform that supports counting of `cycles`,
`instructions`, `branches` and `cache-references` events through the core
performance monitoring unit.

Here are some results from a system running an AMD Ryzen 5500U processor with
dual-channel 16GB DDR4-3200 CL22 memory. Software packages used are `gcc` and
`g++` version 12.2.1, `go` version 1.18.6 and `rustc` version 1.63.0.

## C
```
          2,20,425      cycles:u
          1,33,608      instructions:u            #    0.61  insn per cycle
            27,003      branches:u
            13,277      cache-references:u
```

## C++
```
         19,98,104      cycles:u
         30,85,586      instructions:u            #    1.54  insn per cycle
          4,76,677      branches:u
            68,147      cache-references:u
```

## Go
```
          5,37,115      cycles:u
          5,41,803      instructions:u            #    1.01  insn per cycle
          1,01,532      branches:u
            45,108      cache-references:u
```

## Rust
```
          3,86,711      cycles:u
          3,12,659      instructions:u            #    0.81  insn per cycle
            61,702      branches:u
            22,074      cache-references:u
```

N.B. This is a simple demonstration of resource usage and is by no means a
scheme for ranking programming languages.
