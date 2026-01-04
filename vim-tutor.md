# VIM TUTOR LESSONS

## LESSON 1

1. The cursor is moved using either the arrow keys or the hjkl keys.
   h (left) j (down) k (up) l (right)

2. To start Vim from the shell prompt type: vim FILENAME <ENTER>

3. To exit Vim type: <ESC> :q! <ENTER> to trash all changes.
   OR type: <ESC> :wq <ENTER> to save the changes.

4. To delete the character at the cursor type: x

5. To insert or append text type:
   i type inserted text <ESC> insert before the cursor
   A type appended text <ESC> append after the line

NOTE: Pressing <ESC> will place you in Normal mode or will cancel
an unwanted and partially completed command.

## LESSON 1.2

1. To delete from the cursor up to the next word type: dw
2. To delete from the cursor up to the end of the word type: de
3. To delete from the cursor to the end of a line type: d$
4. To delete a whole line type: dd

5. To repeat a motion prepend it with a number: 2w
6. The format for a change command is:
   operator [number] motion
   where:
   operator - is what to do, such as d for delete
   [number] - is an optional count to repeat the motion
   motion - moves over the text to operate on, such as w (word),
   e (end of word), $ (end of the line), etc.

7. To move to the start of the line use a zero: 0

8. To undo previous actions, type: u (lowercase u)
   To undo all the changes on a line, type: U (capital U)
   To undo the undos, type: CTRL-R

## LESSON 1.3

1. To put back text that has just been deleted, type p . This puts the
   deleted text AFTER the cursor (if a line was deleted it will go on the
   line below the cursor).

2. To replace the character under the cursor, type r and then the
   character you want to have there.

3. The change operator allows you to change from the cursor to where the
   motion takes you. eg. Type ce to change from the cursor to the end of
   the word, c$ to change to the end of a line.

4. The format for change is:

   c [number] motion

## LESSON 1.4

1. CTRL-G displays your location in the file and the file status.
   G moves to the end of the file.
   number G moves to that line number.
   gg moves to the first line.

2. Typing / followed by a phrase searches FORWARD for the phrase.
   Typing ? followed by a phrase searches BACKWARD for the phrase.
   After a search type n to find the next occurrence in the same direction
   or N to search in the opposite direction.
   CTRL-O takes you back to older positions, CTRL-I to newer positions.

3. Typing % while the cursor is on a (,),[,],{, or } goes to its match.

4. To substitute new for the first old in a line type :s/old/new
   To substitute new for all 'old's on a line type :s/old/new/g
   To substitute phrases between two line #'s type :#,#s/old/new/g
   To substitute all occurrences in the file type :%s/old/new/g
   To ask for confirmation each time add 'c' :%s/old/new/gc

## LESSON 1.5

1. :!command executes an external command.

   Some useful examples are:
   (Windows) (Unix)
   :!dir :!ls - shows a directory listing.
   :!del FILENAME :!rm FILENAME - removes file FILENAME.

2. :w FILENAME writes the current Vim file to disk with name FILENAME.

3. v motion :w FILENAME saves the Visually selected lines in file
   FILENAME.

4. :r FILENAME retrieves disk file FILENAME and puts it below the
   cursor position.

5. :r !dir reads the output of the dir command and puts it below the
   cursor position.

## LESSON 1.6

1. Type o to open a line BELOW the cursor and start Insert mode.
   Type O to open a line ABOVE the cursor.

2. Type a to insert text AFTER the cursor.
   Type A to insert text after the end of the line.

3. The e command moves to the end of a word.

4. The y operator yanks (copies) text, p puts (pastes) it.

5. Typing a capital R enters Replace mode until <ESC> is pressed.

6. Typing ":set xxx" sets the option "xxx". Some options are:
   'ic' 'ignorecase' ignore upper/lower case when searching
   'is' 'incsearch' show partial matches for a search phrase
   'hls' 'hlsearch' highlight all matching phrases
   You can either use the long or the short option name.

7. Prepend "no" to switch an option off: :set noic

> FOR CODERS!

1. For coding, I want to select the text inside brackets, curly braces,
   parenthesis, etc.

   Type vi followed by what you want to select inside:
   'vi[' to select the text inside brackets []
   'vi(' to select the text inside the parenthesis

   To _change_ things inside I would use 'c' instead if 'v'
   'ci('
   etc

2. To select a block of text at the beginning and the end. This is great to add
   code to several lines at the same time!

a. To select vertically, enter visual BLOCK mode with <CTRL-V>, then go down 'J'
b. Go to insert mode with capital 'I' and then type what you want to add.

1. To add at the end, we still select all the lines as above, then instead of 'I'
   we do 'A' (append at the end), and add what we need.

2. To fix indentation on the whole file
   a. We have to do 'gg' to go to the top of the file, then =, then 'G'
   b. Here we did it to a whole file, but we can do the same with a selection

3. If we want to work on something else, we can suspend Vim by pressing 'CTRL-Z'.
   We can go back to Vim by typing 'fg' to return to Vim

4. To open an URL, we highlight the URL, then type 'gx' (go to executable)

5. Another way to do changes to multiple lines is by using ":norm! <sequence>"

You can select multiple lines and call a sequence of key strokes on each one.
Example: select in visual mode a few lines and type: ":norm! 0wiprefix "
or ":norm! A // some comment". It works basically like running a macro on each line

1. To quickly move vertically, use <CTRL-U> and </CTRL-D>

## Lesson 1.7
