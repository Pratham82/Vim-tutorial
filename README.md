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
**Named register:**
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
