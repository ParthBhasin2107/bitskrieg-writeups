# Quizploit - Binary Exploitation


## Approach
- went through the source code after installing it
- noticed hexadecimals being used, converted them to decimal for ease
- noticed buffer[] is defined with size 21 but input allows upto 144 chars
- noticed win was defined but was never called, needs some debugger to call it by pausing the program mid run
- used file vuln, noticed "not stripped" then ran strings vuln, but obviously it didn't have the flag 
- checked hint, and got to know it is a quiz ;-;
- started off with the quiz, got first few right
- got stuck and went back to learning

## Solution
answers-
	64-bit
	dynamic
	not stripped
	21
	144
	yes
	fgets
	win
	buffer overflow
	123
	nx
	ROP
	0x401176
- Solved after finding out about the topic


## Flag
picoCTF{my_bIn@4y_3xpl0it_fL@g_7e4d85f6}

## Takeaway
Sometimes read hints
