# 1. IQ test

> logic gates

## Solution:

- we first convert the 10 base decimal to 2 base decimal (which provides us the input for the 36 input points). after that we make a logic circuit simulation and plug in the values. the final output we get is 000100000000


## Flag:

```
nite{000100000000}
```

## Concepts learnt:

- different types of logic gates

## Resources:

- online conversion of bases


***

# 2. I like Logic

> Logic 2 software

## Solution:

- we use Logic 2 software to decode the .sal file and analyse the signal. I used the "Async Serial" analyzer to decode the captured signal, which revealed the flag in hex format


## Flag:

```
nite{000100000000}
```

## Concepts learnt:

- information can be transmitted through digital signals. we can use Logic 2 to analyse this signal and use its inbuilt analyzers to decode the signals

## Resources:

- Logic 2 software


***

# 3. Bare Metal Alchemist

> Logic 2 software

## Solution:

- using the GNU toolchain, we find out that the file was for an 8-bit AVR microcontroller. we diassembled the file with avr-objdump searched the main function. we them find out the program was XOR cipher. we then decrypt the message and get our flag


## Flag:

```
TFCCTF{Th1s_1s_sOm3_s1mpL3_:rdu1no_f1rmw:re}
```

## Concepts learnt:

- avr-objdump is a command-line program used to display information about compiled object files and executables, specifically for the AVR microcontroller architecture

## Resources:

- google to decrypt the cipher and how to interact with .elf files


***