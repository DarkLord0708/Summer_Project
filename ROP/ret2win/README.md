Had to call the ret2win function, using gdb got to know that the input being taken was only of size 40 and 4 bytes offset also the read function was taking a larger input, i.e. size 56 so we can overflow that and reach the desired function.
This was achieved usnig the exploit.py
