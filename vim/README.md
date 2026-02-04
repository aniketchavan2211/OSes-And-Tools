# VIM Text Editor Notes

## Installation

First install vim on debian based system using apt package manager,
consider checking for other distros online.

```bash
sudo apt -y update
sudo apt install -y vim
```

Also check where is vim binary stored and loaded from. Not much of Important for now, but still help a lot further.

```bash
which vim
```

Normally you get output:
```bash
/usr/bin/vim
```

## Getting Started with VIm Text Editor

Start vim on terminal by enter this command `vim` on terminal windows:
```bash
vim
```

Also you can open or create file before hand like this one:
```bash
vim text01.txt
```

I create a `text01.txt` text file newly, if file is already has been created then it will just open to edit the file.

## Vim Modes

Very Important to understand this things.

1. **Normal Mode ( Command Mode )**
2. **Command-line Mode**
3. **Insert Mode**
4. **Visual Mode**

### Normal Mode

***What is Normal Mode ?***
> Normal Mode what you enter by default on first opening vim text editor. From here you switch to others Modes, Think it like a Terminal, but only vim commands will work. ***`Not Shell commands`***.

***What is Insert Mode ?***
> Now, that you open vim, let's write something in file, you have switch to `INSERT MODE`, then only you are able to write to the file.

To switch to `INSERT Mode` you enter ***`i`***. key on keyboard. And you get back to Normal / Default / Command Mode by `ESC` KEY.

***What is Visual Mode***
> Suppose you, just don't change text written on file, moving on text and selecting and copy / cut and paste them.

This where Visual Mode plays, it lets you select text and copy/cut and paste
them without writing to file.

Visual Mode does not write to text only hightlight the selected text.

## File Operations

### Create a File / Edit

To Create a file in VIm Text Editor, in Normal Mode, enter
`:edit filename.extension`.

Example : :`edit text02.txt` this lets you create a `text02.txt` text file with named **text02**. If file already has been exist or created then it open and you can edit it.

In Normal Mode, You are unable you write to text to file. You only write in entering into `Insert Mode` and that is done by `i`.

You can write anything you want in Insert Mode.

To get back to Normal / Default / Command Mode. Type `ESC` key. It let you enter in Normal Mode.

### To Save a File

Basic operation after writing to something to file. to save it. we doing in Normal Mode ( Default / Command ).

If you are in Insert or Visual Mode , EXIT by `ESC`. then type ***`:w`***

```bash
:w
```

It lets you write to the file. the content written on file will get saved successfully.

### To Quit

To exit VIm Text Editor, Enter into Normal / Default / Command Mode then,
Type ***`:q`*** it literally translate to **quit**.

### Save & Quit

Suppose to want Save content of file / write to the file, and quit or exit the vim text editor.

Enter into Normal / Default / Command Mode, Type ***`:wq`***.

```bash
:wq
```

### To Edit the file

To edit already created file, On terminal type vim filename.txt,
```bash
vim file01.txt
```

This will open vim text editor opening already created file named `file01.txt` If in case if has not exist or not created then it will create for you.

### Quit w/o Saving

Suppose you type something in file, but not save or write to the file,
and you want quit without making changes to file and quit / exit the vim.

Then Type ***`:q!`***.

Remember You should be in Normal Mode, to work this command.

This lets you exit / quit vim without changing content of file. that made earlier , if changes written then *NO USE*.

## Visual Mode

To Copy the selected text copy / cut somewhere else. To do that you have switch to Visual Mode from Normal Mode, `v`, First if you are in Insert Mode, or others mode. Switch back to Normal Mode, then Visual Mode.

Insert Mode --> Normal Mode --> Visual Mode

TO enter into Visual Mode you have enter ***`v`*** in Normal Mode.

Now to confirm that, you see something like `-- VISUAL --` text at bottom this you successfully entered into visual mode.

Now that you enter into visual mode, take your cursor to first letter of word. The selected text will be highlighted. before entering into visual mode, you need you place your cursor to origin or first letter to copy / cut.

Move your cursor left right to adjust, once text is selection is done

TO **COPY** : type ***`y`***

TO **CUT** : type ***`d`***

after `y` or `d` is key is pressed , move your cursor to where you have to copy or cut selected text.

Pressed ***`p`*** ( lowercase ) to paste the text after the cursor, meaning the selected text will paste after the cursor. you may place at beginning of the starting letter.

Pressed ***`P`*** ( UPPERCASE ) to paste the text before the cursor, likewise the select text will be paste before cursor. so may have place cursor at the end of word.

## Find & Replace

To search / Find / Locate text in file, and replace with other one. then using a simple command pattern. You have enter into Normal Mode, if already in some mode exit the mode by `ESC` key.

```bash
:%s/to-searched-text/get-replace-text/g
```

- `:` : collon indicates you giving an vim command.
- `%s` : indicates replaces the content in the entire file.
- `to-searched-text` :  The word `to-searched-text` is will be searching in entire file.
- `get-replace-text` : The `to-searched-text` get replace with `get-replace-text`.`g` :  stands for global.

Another Detailed one for Find & Replace.

The command is :
```bash
:2,3s/Hi/Hello and Welcome/gci
```

- `2,3` signify 2nd and 3rd line of file.
- find `Hi` and replace with `Hello and Welcome` making it ask for each occurrence.

It will ask confirmation:

- `y` - Replace the match
- `n` - Skip the match
- `a` - Substitutes the match and all remaining occurrences of the match
- `q` or `Esc` - Quit substitution
- `l` - Replace the match and quit
- `CTRL+Y` - Scroll the screen down
- `CTRL+E` - Scroll the screen up

Pressed `y` for change or replace the searched text / content.

## Undo & Redo

To undo pressed or type `u` key in Normal Mode.

And to redo pressed `CTRL+R` key, to do undo mutliple times, you can do this with number prefix like `2u` do undo 2 times. `n2` n means no. of times and u means execute undo operations.

to list undo options type `undolist` in Normal Mode.
```bash
:undolist
```

Extra Tips typing `dw` deletes complete word in Normal Mode Be carefull always watch which mode are you in.

## Reference
-  [Vim Beginners Guide](https://www.freecodecamp.org/news/vim-beginners-guide/)
