# Vim tutorial
This is file contains all the instructions that will require for learning vim.

## Contents
#### 1. Basics  
#### 2. Navigation  
#### 3. Help system  
#### 4. Deleting text  
#### 5. Putting text  
#### 6. Yanking text  
#### 7. Undo redo  
#### 8. Registers  
#### 9. Inserting text  
#### 10. Replacing text  
#### 11. Lower case or upper case  
#### 12. Joining text
#### 13. Searching & Finding text 
#### 14. Substituting text

### 1. Basics:
-----------------------------------------------------------
**Normal mode/Command mode** 
```
ESC key
```
**Insert mode** 
```
 i
```
**Save file** 
```
:w
```
**Save and close file**
```
:wq 
```
**Close file**
```
q
 ```
**Close file without saving**
```
:q!
```
 * **Open file**  
 ```
 vim filename.extension
 ```

### 2. Navigation
-----------------------------------------------------------
**Move down**
 ```
 j
  ```
  
**Move up**
``` 
k
```
**Move right** 
```
l
```
**Move left** 
``` 
h
```
​**To​ ​move​ ​down​ ​one​ ​page** 
``` 
Ctrl-f​​​ 
``` 

​**To​ ​move​ ​up ​one​ ​page**
``` 
​​Ctrl-b​​​ 
``` 
**Go next one word**
``` 
w (Consider punctuation as a word)
W (Ignores punctuation)
``` 

**Go back one word** 
```
 b (Consider punctuation as a word)
 B (Ignores punctuation) 
```
**Go to beginning of line**  
``` 
0
``` 

**Go to first character ** 
``` 
 ^ (shift 6)
``` 
**Go to end of line**  
``` 
$ (shift 4)
``` 
**Go to the beginning of file** 
``` 
gg
``` 
**Go to the end of file** :  
 ***[line no.]gg***   
``` 
12gg
``` 
**Go to specific line (using line mode)**
***: [line no.]*** 
``` 
:45
``` 
**Find how many lines in file** 
``` 
Ctrl + g
``` 
**Keep the cursor and move file up** 
``` 
z + enter
``` 
### 3. Help system
-----------------------------------------------------
**Open help file**
``` 
:help
```
**Close help** 
``` 
:q
```
**Finding help for specific command** 
***: help [command]***
``` 
:help dd
```
**Go back to previous section** ​​
``` 
Ctrl+ o
```
**Go Forward one page** ​​
``` 
Ctrl+ i
```
**Go to specific section** 
**Get cursor under the topic** 
``` 
Ctrl-]
```
**Switch to the file/help** 
``` 
Ctrl+ w w
```
**Find the command name** - 
``` 
:h :d(your command)
Ctrl + d
```
**Switch between the command results** 
``` 
tab
```
**Wild menu** 
``` 
:h 'wildmenu'(Shows status bar)
```
**Quit help**
``` 
:q
```

### 4. Deleting text
---------------------------------------------------
**d: stands for delete**
**Delete character at current cursor position** 
``` 
x
```
**Delete character at before (left to)cursor position**
``` 
X
```
***d = operator*** 
***w = word motion***

**Delete word after the cursor**
``` 
dw
```
**Delete word after cursor with punctuation**
``` 
dW
```
**Delete word before the cursor**
``` 
db
```
**Delete word before cursor with punctuation**
``` 
dB
```

**Delete character at current cursor position**  
``` 
dl
```
**Delete character at before (left to)cursor position**
``` 
dh
```
**Delete current line and one line below it**
``` 
dj
```
**Delete current line and one line above it**
``` 
dk
```
**Delete from current cursor till the beginning of line**
``` 
d0
```
**Delete from current cursor till the end of line**
``` 
d$ /D
```
**Delete whole line**
``` 
dd
```
**Delete specific number of lines**
***[no. of lines] dd***
``` 
4dd 
```
**Repeat the previous command** 
``` 
.
```
**Some combinations of operators and motion with counts**
***
***[count]operation {motion}***
***5dw***
***5 = The count/ how many time to repeat***
***dw = The command(Delete word)***

***[count]operation[count] {motion}***
***3w = Repeat word motion 3 times.***
***d3w = Delete the 3w motion.***
***2d3w = Delete 3 words motion 2 times.***

### 5. Putting
--------------------------------------------------
**p:  stands for put/paste**
**1. For characters or words**
**put/paste the copied/deleted line after current cursor position**
``` 
p
```
**put/paste the copied/deleted line before current cursor position**
``` 
P
```
**2. For whole line**
**put/paste the copied/deleted line below current cursor position - **
``` 
p
```
**put/paste the copied/deleted line above current cursor position - **
``` 
P
```
***Standard vs. Vim***
***cut - delete***
***copy - yank***
***paste - put***

### 6. Yanking
--------------------------------------------------------------
**y: stands for yank**
**Copy word after the cursor**
```
yw
```
**Copy word after cursor with punctuation**
```
yW
```
**Copy word before the cursor**
```
yb
```
**Copy word before cursor with punctuation**
```
yB
```

**Copy character at current cursor position**
```
yl
```
**Copy character at before (left to)cursor position**
```
yh
```
**Copy current line and one line below it**
```
yj
```
**Copy current line and one line above it**
```
yk
```
**Copy from current cursor till the beginning of line**
```
y0
```
**Copy from current cursor till the end of line**
```
y$ / Y
```
**Copy whole line**
```
yy
```
**Copy specific number of lines**
***[count]yy***
```
4yy
```
### 7. Undo & redo
-----------------------
Undo last change - u
Redo last change - Ctrl + r

### 8. Registers
------------------------------------------------
**reg stands for register**

***Registers are storage locations***

**1. Unnamed ("")**
**2. Numbered ("0... "9)**
**3. Named ("a..."z)**

***"" holds text from d,c,s,x and y operations.***
***"0 holds last text yanked (y).***
***"1 holds last text deleted d ot changed c.***
***Numbered registers shift with each d or c.***

**Check all registers**
```
:reg 
```
**Check specific register**
***:reg[register name]***
```
:reg d
```
**List multiple registers- **
***:reg[register(s)]***
```
:reg ghf
```
**Put the last yanked text- **
```
"0p
```
**Delete text without affecting normal registers:** 
***(black hole register)***
```
"_d
```

**Put the specific deleted, yanked or changed register**
```
"3p
```
**2. Named register:**
```
cyy
```
***Yank a line to a specific register***
***"[register name]operation***
```
"ayy
```
***Put the specific deleted, yanked or changed text to a register***
```
"ap
```
***For appending a line to already filled register:***
***"[Upper case of that alphabet]operation***
```
"Ayy 
```
Repeating with registers:
***[count][register]operator***
```
4"gp
```
***[register][count]operator*** 
```
"g4p
```
It  will paste the text yanked in register p 4 times 

### 9. Inserting
-------------------------------------------------------
** i stands for insert**
**Insert mode**
```
i
```
**Insert text before current cursor position**
```
i
```
**Go to the first non blank character in line and insert mode**
```
I
```
**Insert text after current cursor position**
```
a
```
**Go to the last non blank character in line and insert mode**
```
A
```
**Insert text below the cursor**
```
o
```
**Insert text above the cursor**
```
O
```

**Repeat the command**
***[count]operation[word/character]esc***
```
12iHold + esc 
```
***(This command will create single line containing hold 12 times)***

```
12oHold + esc 
```

***(This command will create 12 lines containing hold, below the cursor )***

```
12OHold + esc 
```

***(This command will create 12 lines containing hold, above the cursor )***


### 10. Replace mode
-------------------------------------------------------------
**r stnads for replace**
**Enable replace mode (Whatever we write will be overwrite the existing text)**
```
R
```
**Replace single character**
```
r
```
**c stands for change**
**Replace single word with one word or multiple words-  **
***(change word)***
```
cw
```
**Replace from current cursor position to the end of the line - **
```
c$ / C
```
**Replace from current cursor position to the star of the line**
```
c0
```
**Replace whole line** 
```
cc
```
**Using it multiple times**
***[count]cc***
```
3cc
```

### 11. Lowercase & Uppercase
------------------------------------------------------------------
**Change the case of character below cursor**
```
~
```
**g  stands for global**
**Change the case of the word**
```
g~w
```
**Change the case of the line from current cursor position**
```
g~$
```
**Change the case of the whole line**
```
g~~
```
**Make every character in a word uppercase**
```
gUw 
```
**Make every whole line uppercase**
```
gUU
```
**Make every character in a word lowercase**
```
guw
```
**Make every whole line lowercase**
```
guu
```

### 12. Join
--------------------------
**J stands join**
**Join lines(go t first line)**
```
J
```
***If there is space after first line it will append 1 space.*** 
***If there is period. after first line it will append 2 spaces.***
**Join lines without spaces**
```
gJ
```
**Join multiple lines**
***[count]J***
 ```
 4J
```

### 13. Search find and replace
---------------------------------------------------------

**find single character in a line**
**f stands for find** 
**t stadnds for till**
**Search forward to the cursor on the line** 
***f{character}*** 
```
fd
```
**Search backward to the cursor on the line**
***F{character}*** 
```
Fd
```
**Position cursor one position before given character**
***t{character}***
```
tb 
```
**Position cursor one position after given character**
***T{character}***
```
Tb
```
**Repeat forward search**
***[count]f{character}***
```
3fa
``` 
**Combining t with delete **
***[delete][till]{character}***
```
dtp 
```
**Repeat forward search in same direction**
``` 
;
```
**Repeat forward search in opposite direction** 
```
,
```

**13.2 Search for entire word or series of characters**
**Search for entire word or series of characters in same direction of cursor**
***: /{word/characters}***
```
/dog + Enter
```
**Repeat forward search in same direction**
```
n
```
**Repeat forward search in opposite direction**
```
N
```

***Performing search and replace word common pattern***
**Find word and** 
***/{word/characters} ***
```
/and
```
**Change the word and to &**
*** [change][word]{new word} ***
```
cw& + esc
```
**Go to the next occurrence of and**
***[next]***
```
n
```
**Repeat previous command**
```
.
```

**Search backward from current cursor position**
***?{word/characters}***  
```
?and + enter
```
**Repeat backward search in same direction**
```
n
```
**Repeat backward search in opposite direction**
```
N
```
**Search forward for occurrence of the word under /near the cursor**
```
 *
```
****will match the entire word and skips the word containing same characters.***
**Repeat forward search in same direction**
```
 */n
 ```
**Repeat forward search in opposite direction**
```
N
```
**Search backward for occurrence of the word under /near the cursor**
```
#
```
**Delete from current cursor position till search result**
***[delete]/{word/characters}***
```
d/hire
```

### 14. Substituting
---
**s stands for substituting**

**To change the word in the current line from old to new**
***:[substitute]/{old word}/{new word}***
```
 :s/cpu/CPU 
```

***[flags] - :s/{old}/{new}/[flag]***
**To change the word in the current line from old to new with flags**
***:[substitute]/{old word}/{new word}/[flags]***
```
:s/cpu/CPU/h 
```

**To change every occurrence of the word on the same line from old to new with global flag** 
***:[substitute]/{old word}/{new word}/g***
```
:s/cpu/CPU/g
```

***[range] - :[range]s/{old}/{new}/[flags]***
**Default range is current line, thats why our substitution occurs on the same line only**
**Range is one or more line specifier separated by , or ;**

**Ranges:**
**1. Line no**

**For a single line**
***:[line no.][substitute]/{old word}/{new word}/[flags]***
```
:41s/luke/duke/g
```

**For multiple lines (It will operate on given line range)**
***:[starting line no. , ending line no.][substitute]/{old word}/{new word}/[flags]***
```
 :10,20s/Mark/Dark/g
 ```

**Special characters:**
***$ =last line , . = current line , % all lines(entire file) =(1,$)***

**Operate from current line till the line**
***:[current line, last line.][substitute]/{old word}/{new word}/[flags]***
```
 :.,$s/Mark/Dark/g
 ```

**Operate on all lines** 
***:[all lines][substitute]/{old word}/{new word}/[flags]***
```
:%s/python2/python3/g 
```

**Operate on specific pattern**
 ***:[/Pattern -1/],[/Pattern -2/][substitute]/{old word}/{new word}/[flags]***
```
:/Global/,/Local/s/net/org/g
```
***This will change net from org between our search pattern***

**Combine search patterns with line number/ special characters**
***:[/Pattern - 1],$[substitute]/{old word}/{new word}/[flags]***
```
:/Local/s/net/org/g
```

**Change the patterns on current line and all its occurrences**
***pattern separators | , # + - =***
***:[substitute][pattern separator][old pattern][pattern separator][new pattern][pattern separator]*** 
```
:s#old/variable#new/variable#
```
**Summary for substituting**

**1. Same line search** 

***f{char} - Forward search***

***F{char} - Reverse search***

***t{char} - Forward search till***

***T{char} - Reverse search till***

***; - Repeat in the same direction***

***, - Repeat in the opposite direction***

**2. For whole file**

***/{pattern} - Forward search***

***?{pattern} - Reverse search***

***n - Repeat in the same direction***

***N - Repeat in the opposite direction***

***#- Reverse search for word***
