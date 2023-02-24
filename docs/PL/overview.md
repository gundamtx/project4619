# Overview of Compiler, Assembler, and Linker

This is the high-level overview of how we convert high level language source code such as C into executable.

```mermaid
graph LR;
  HLL[High level language] -. Compiler .-> ASM[Assembly source]
  ASM -. Assembler .-> OBJ["Object file(binary)"]
  OBJ -. Linker .-> EXE[Executable]
```

:::info
For example of gcc, we can use these commands to generate those files.

- `g++ something.c` (compiles, assembles, and links to produce an executable a.out)
- `g++ -S something.c` (produces an assembly file something.s)
- `g++ -c something.c` (produces an object file something.o)
- `g++ something.s` (assembles and links to produce executable a.out)
- `g++ something.o` (links to produce executable a.out)
:::

```mermaid
graph LR;
    s1(Source code)-->c1{{Compiler}};
    s2(Source code)-->c2{{Compiler}};
    s3(Source code)-->c3{{Compiler}};
    c1 --> asm1(Assembly file);
    c2 --> asm2(Assembly file);
    c3 --> asm3(Assembly file);
    asm1 --> a1{{Assembler}};
    asm2 --> a2{{Assembler}};
    asm3 --> a3{{Assembler}};
    a1 --> o1(Object file);
    a2 --> o2(Object file);
    a3 --> o3(Object file);
    o1 --> l{{Linker}};
    o2 --> l;
    o3 --> l;
    pl((Program Libraries)) --> l;
    l --> e(Executable file);
```

## References

- <https://courses.engr.illinois.edu/cs232/sp2009/lectures/Examples/lecture6/lecture6.html>
- <https://cs3157.github.io/www/2022-9/lecture-notes/03-compile.pdf>
