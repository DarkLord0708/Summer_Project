pwnme function was calling three other functions callme1, callme2, callme3 and they were checking for arguments that were namely deadbeef, cafebabe, doodfood.
I used the rop gadget pop esi; pop edi; pop ebp; ret
and took the addresses of respective functions from gdb.
This was achieved using the exploit.py
