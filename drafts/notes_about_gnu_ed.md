# Notes about GNU `ed`

This draft contains notes and informations about GNU `ed` line editor. It is intended for help
with the development of `eddie`, a line editor similiar to `ed`.

# General
- `ed` is a modal editor (i.e. it has modes)
- There are 2 modes in `ed`: Prompt and Input mode
		- Prompt mode allows for inputting commands (Similiar to Command mode in Vim)
		- Input mode allows for inputting text to the buffer (Similiar to Insert mode in Vim)

# Prompt mode
- By default `ed` is automatically in prompt mode, so we usually don't need to do the switch
- To switch to Prompt mode, we need to use `P`
- `ed` uses `*` for Prompt mode (to avoid confusion with `sh`'s `$`, which I think is not very necessary today)
- Prompt mode has several commands:
	- `!` allows for executing shell commands
	- `r` writes the input file into the buffer
		- NOTE: `r` is also used to write shell command output to the buffer
	- `p` prints the last line of the buffer
	- `,`, when stand alone, works the same way as `p`, but when combined with other commands means `the whole buffer`
	- `w` followed by an input file writes the content of the buffer to the file
	- `a` allows for appending text to the buffer
	- `s` is used for search-and-replace
	- `<n: integer>` moves the cursor to line `n`
	- `m<n>` moves the line at the cursor to line `n`

# Input mode
- Input mode is enabled when an input command (such as `a`, `i`, `c`) is used
- In input mode, every text that is inputted gets put in the buffer
- `.` is used to terminate input mode

# Examples

Write a file into the buffer:

```
*r a.tcl
94 (Bytes written)
```

Print the whole buffer:
```
*,p
#!/bin/tclsh

set i 0
gets stdin i
if {$i == 0} {
	puts 0
} else {
	while {1} {
		puts 1
	}
}
```

Correct a mistake:
```
a
There is an foutain.
Some more fountains.
.
# Select line 1 for editing
1
There is an foutain.
# Correct the spelling of "fountain"
s/outa/ounta/p
There is an fountain.
```
