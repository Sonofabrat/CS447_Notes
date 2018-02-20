## CS 447 Exam 1 Reference Sheet
#### Andrew Ryan

##### MIPS

	- Formula for I type Immediate:
		
		- Destination PC = Start PC + 4 + (SignExt(Imm)*4)

		- Quick and dirty hack: Starting at instruction, count instructions until destination, subtract 1 (or start at next instruction)

	- Formula for J type address:

		- Destination PC = Address*4

		- Quick and dirty hack: Divide destination PC/4

	- Instruction format:

		- 32 bits long

		- R-type
		┏━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━━━┓
		┃	OPCODE	┃	  RS	┃	  RT	┃	  RD	┃	SHAMT	┃     FUNCT   ┃
		┃	6 bits	┃	5 bits	┃	5 bits	┃	5 bits	┃	5 bits	┃	 6 bits   ┃
		┗━━━━━━━━━━━┻━━━━━━━━━━━┻━━━━━━━━━━━┻━━━━━━━━━━━┻━━━━━━━━━━━┻━━━━━━━━━━━━━┛

		- I-type

		┏━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
		┃	OPCODE	┃	  RS	┃	  RT	┃			 IMMEDIATE				┃
		┃	6 bits	┃	5 bits	┃	5 bits	┃			  16 bits				┃
		┗━━━━━━━━━━━┻━━━━━━━━━━━┻━━━━━━━━━━━┻━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛

		- J-type

		┏━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
		┃	OPCODE	┃	  					ADDRESS 							┃
		┃	6 bits	┃						26 bits								┃
		┗━━━━━━━━━━━┻━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛

##### Binary Digits:

	  128    64     32     16     8      4      2      1
	______ ______ ______ ______ ______ ______ ______ ______
	   8      7      6      5     4      3      2      0   


##### Hex Conversions:

	0  | 1  | 2  | 3  | 4  | 5  | 6  | 7  | 8  | 9 | A  | B  | C  | D  | E  | F
    ____________________________________________________________________________
	0  | 1  | 2  | 3  | 4  | 5  | 6  | 7  | 8  | 9 | 10 | 11 | 12 | 13 | 14 | 15

##### Signed Numbers:
	
	Sign-Magnitude:
		- Must know number of bits
		- MSB represents sign
		- 1 = negative, 0 = positive

	One's Complement:
		- MSB represents sign
		- 1 = negative, 0 = positive
		- If MSB is 1, flip all bits
		- Has representations for 0 and -0

	Two's Complement:
		- MSB represents sign
		- 1 = negative, 0 = positive
		- If MSB is 1, flip all bits and add 1
		- Only has representation for 0