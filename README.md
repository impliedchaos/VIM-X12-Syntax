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

## Also
- This has most segment names from X12 versions 2000 to 6040
- Doesn't include support for mailbag envelopes
- Probably need to add transactional acknowledgment segments, but nobody I deal with uses them.  Adding "TA1|TA3" to the x12Envelope regular expressions is easy, if you need them.
