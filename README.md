# WTFC
WTFC - minimalistic 8-bit console that works f\*ck knows how and uses BrainF\*ck as a programming language. It has 32x24, 2b screen and 24KB of memory for 16 programs.

Inspired by:
- [BrainF\*ckConsole74](https://brainfuckconsole74.ch/) by AndOr
- [4BOD](https://puarsliburf.itch.io/4bod-fantaly-console) by puarsliburf


## PROGRAM, "DISK"
1. 4096 commands/characters can be used in any program.
1. All characters except < > , . [ ] + - are ignored by the interpreter, but take up space in memory.
1. There are 16(0-f) lines in file "Memory.bf", each of which is a separate program.
1. When the console is turned on, program 0 starts.
1. You can switch between programs only after turning on the console, this will be discussed in more detail later.
1. There is already a program installed on this fantasy console: "Tiny" by Yurix, you can delete it any time.


## RAM
1. There are 256 memory cells in RAM, each of which is an 8-bit number, from 0 to 255.
2. If you increase the cell with a value of 255, it will be 0.
2. If you decrease the cell with a value of 0, it will be 255.
2. If you move to the left from the cell number 0, you will get into the cell number 255.
2. If you move to the right from the cell number 255, you will get into the cell number 0.
2. Cells from 0 to 251 are normal RAM cells.
2. Cell 252 is responsible for the speed and stability of the program: if it is equal to 0, then stable mode is turned on (fairly stable fps, but not high), otherwise maximum performance mode is turned on (not stable fps, but it becomes as high as possible.
2. Cell 253 is responsible for the screen resolution, if it is 0 then the resolution = 32x24 otherwise 16x12
2. Cell 254 is responsible for the current executable program, if you set it to a value from 0 to 15, then the selected program will start on the next frame, if the value is greater than 15, the console will turn off.
2. Cell 255 sets to zero every frame.
 
 
## OUTPUT, SCREEN
1. Screen is 32x24(4:3), 2-bit, also can be 16x12.
2. The screen supports 4 colors: black, dark gray, light gray, white.
3. When using the "." command, the color is displayed based on the remainder of dividing the cell value by 4.
 

## INPUT, KEYBOARD
When using the "," command, the sum depending on the pressed keys is entered into the cell.
- 128 - down arrow
- 64 - up arrow
- 32 - right arrow
- 16 - left arrow
- 8 - space
- 4 - return
- 2 - Z
- 1 - X


## PROGRAMMING LANGUAGE, BRAINF\*CK
1. Basics:
```brainfuck
+   increases current cell value
-   decreases current cell value
<   decreases memory pointer
>   increases memory pointer
[   while value in current memory cell != 0
]   end while
.   draws on screen current cell value
,   gets input from keyboard
```
2. Tricks:
```brainfuck
[-]                 sets current value to 0
[>+<-]              moves value to next cell
[<]                 moves left while cell not equals 0
[>]                 moves right while cell not equals 0
[>+>+<<-]>>[<<+>>-] copies value to next cell
+>+[<+>-]           summation
+>+[<->-]           substraction
+[>+++<-]           multiplication
+[>---<-]           division
```
3. If Statement:
```brainfuck
+++++[>>+>+<<<-]>>>[<<<+>>>-]>+<<[-----[>]]>>[<<<+++>>>[-]]
```


## EASIER PROGRAMMING, BFML
1. For simpler programming, you can use BFML.exe, this program removes comments starting with #, and also allows you to write on various lines, using indents. In order to compile a file, you need to run this program and then enter the name of the file, you do not need to enter the full path, the file must have the extension ".bf".
2. You can also use syntax highlighting for Notepad++, which is located in the main folder.


### Links:
Itch.io: https://itsyurix.itch.io/wtfc
