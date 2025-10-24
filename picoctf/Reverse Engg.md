# 1. GDB Baby step 1

> GNU debugger

## Solution:

- we use the GNU debugger to analyse the file. we first get the info of the functions and see that there is a main function inside which there is eax variable with a value. we convert the value into decimal and submit it in a flag format

```bash
rishi@Rishi-omen-linux:~/picoCTF$ ls
debugger0_a
rishi@Rishi-omen-linux:~/picoCTF$ gdb debugger0_a
GNU gdb (Ubuntu 12.1-0ubuntu1~22.04.2) 12.1
Copyright (C) 2022 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from debugger0_a...
(No debugging symbols found in debugger0_a)
(gdb) info functions
All defined functions:

Non-debugging symbols:
0x0000000000001000  _init
0x0000000000001030  __cxa_finalize@plt
0x0000000000001040  _start
0x0000000000001070  deregister_tm_clones
0x00000000000010a0  register_tm_clones
0x00000000000010e0  __do_global_dtors_aux
0x0000000000001120  frame_dummy
0x0000000000001129  main
0x0000000000001140  __libc_csu_init
0x00000000000011b0  __libc_csu_fini
0x00000000000011b8  _fini
(gdb) disas main
Dump of assembler code for function main:
   0x0000000000001129 <+0>:	endbr64 
   0x000000000000112d <+4>:	push   %rbp
   0x000000000000112e <+5>:	mov    %rsp,%rbp
   0x0000000000001131 <+8>:	mov    %edi,-0x4(%rbp)
   0x0000000000001134 <+11>:	mov    %rsi,-0x10(%rbp)
   0x0000000000001138 <+15>:	mov    $0x86342,%eax
   0x000000000000113d <+20>:	pop    %rbp
   0x000000000000113e <+21>:	ret    
End of assembler dump.
(gdb) p/d 0x86342
$1 = 549698
```

## Flag:

```
picoCTF{549698}
```

## Concepts learnt:

- gnu is a powerful tool in linux commandline used for debugging programs
- 

## Notes:

- gnu also has many useful features within it such as the decimal converter which was used in this challenge

## Resources:

- google for gnu commands


***

# 2. ARM assembly 1

> analyse code

## Solution:

- in the code to 'WIN' we need to make the function LC0 equal to 0. we now solve with w0 as 0 inside the func and follow along the commands which are inside the func. the final hex we get is 001b and to we convert it into the file format

## Flag:

```
picoCTF{0000001b}
```

## Concepts learnt:

- we can analyse the programs to read out the condition which the it is programmed to and find out our desired input

## Resources:

- google on various mathematic command and conversion


***

# 3. Vault door 3

> code analyse

## Solution:

- upon analysing the code, we find out that the program checks the input with a certain character after doing a lot of scrambling. we can unscramble the final comparing text by passing it through the program and get the correct input. we print the buffer and use the correct input in the program to grant access and get our flag

```java
System.out.println(buffer);

```

## Flag:

```
picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_c79a21}
```

## Concepts learnt:

- using the final comparing text to get the correct input
- 

## Notes:

- we can put our own commands in between the code to intercept the data and get useful information

## Resources:

- no refrence


***