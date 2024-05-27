here also in the pwnme function we can overflow the given variable, and we can access a usefulString which reads the flag for us.
we had to make a sys call before calling the string so that the script /bin/cat flag.txt gets run.
this was achieved using exploit.py
