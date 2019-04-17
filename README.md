# VIM-X12-Syntax
Syntax Highlighting of ANSI X12 EDI files for Vim

Unlike the other Vim X12 syntax files I've found, this actually finds the correct delimiters of the file and uses them.  If the segment delimiter is not a linefeed, then it will mark it, and attempt to softwrap on it as well.

## Usage:
Put "x12.vim" it in your ~/.vim/syntax directory, open an EDI document and ":set ft=x12" or ":setfiletype x12".

To automatically set the filetype you can create a ~/.vim/scripts.vim file and inclue the following:
```
if did_filetype()
    finish
 endif
 if getline(1) =~ '^ISA' || getline(2) =~ '^ISA'
    setfiletype x12
 endif
 ```
