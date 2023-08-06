`grep` - search files. There's some interesting history around the name, but this tool is almost 50 years old at the time of writing, and continues to be the ubiquitous tool for searching files (everything in Linux is a file) for matching text.

Some common options:

```
-v -- Show lines that do not match the searched string.
-c -- Show only the count of lines that contain the searched string.
-n -- Show the line number next to the printed lines that match the searched string.
-i -- Ignore case.
-l -- Show only the filename with a matching string. Useful when used to search multiple files...
	-d recurse -- Used when providing a directory as the input file, to read all files under said directory.
		   -- Note when no file is given, the current directory is searched recursively.

References:
[guru99.com](https://www.guru99.com/linux-pipe-grep.html)
[grep(1) - Linux manual page](https://man7.org/linux/man-pages/man1/grep.1.html)

-----

`wc` - count lines, words, and bytes for a file

I often use this command with the `-l` option to count new lines, to either tell how long a file is or when chained with other commands to determine how many occurrences of a pattern matches.

For example, to combine `grep` and `wc`, we can determine how many occurrences of a PATTERN exist in a file (not just how many lines in said file the PATTERN shows up on):

`grep -o PATTERN FILE | wc -l`

The `-o` option for grep outputs the matching PATTERN on a new line for each matching PATTERN. Natively `grep` will print the raw line from the file it is searching. That output is piped into `wc` and we use the `-l` option to count the number of lines. This combination allows us to search for each occurrence of the pattern and return the count. 


