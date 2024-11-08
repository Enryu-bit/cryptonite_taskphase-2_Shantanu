# GDB baby step 1

**Flag:** `picoCTF{549698}`
<br>
Got to know about a highly useful tool named `gdb` which is used to debug programs.<br>
Learnt basic intro on youtube and then proceeded with the challenge.<br>
basically i had to disassemble the main function using gdb and then the value of the flag would be the value inside the eax register in gdb.<br>
Disassembly means that when the compiler takes high level code and convert it in machine code(binary) it is not readable by us but by disassembling it and making it into readable assembly code lets us see somewhat on whats actually happening.<br>
Did the same but my system was not showing me the registers i dont know why but still i tried converting every hexadec value in int and trying the flag and got it finally.<br>
used python to get its int form.<br>
```bash
┌─[user@parrot]─[~/Shared]
└──╼ $gdb debugger0_a
GNU gdb (Debian 13.1-3) 13.1
Copyright (C) 2023 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "aarch64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from debugger0_a...
(No debugging symbols found in debugger0_a)
(gdb) i r eax
The program has no registers now.
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000001129 <+0>:	.inst	0xfa1e0ff3 ; undefined
   0x000000000000112d <+4>:	str	z21, [x2, #74, mul vl]
   0x0000000000001131 <+8>:	casah	w28, w9, [x12]
   0x0000000000001135 <+12>:	.inst	0xb8f07589 ; undefined
   0x0000000000001139 <+16>:	.inst	0x00086342 ; undefined
   0x000000000000113d <+20>:	.inst	0xf390c35d ; undefined
End of assembler dump.
(gdb) exit
┌─[user@parrot]─[~/Shared]
```
```bash
┌─[user@parrot]─[~/Shared]
└──╼ $python
Python 3.11.2 (main, May  2 2024, 11:59:08) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> int(0x00086342)
549698
```
Learnt about gdb and how it can be used to debug and disassemble code in an efficient way.<br>

References <br>
[GDB intro](https://www.youtube.com/watch?v=sCtY--xRUyI)
[Disassemble Guide](https://visualgdb.com/gdbreference/commands/disassemble)
