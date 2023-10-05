# Piff 

Simple File Diff Tool in Python.<br/>  
It's very slow (not only because it's written in Python, but also because it uses O(N²) algorithm) and implemented for educational purposes

## Quick Start

```console
$ ./piff.py diff file1.txt file2.txt > file.patch # generates patch file with list of changes that we need to apply to go from file1 to file2
$ ./piff.py patch file1.txt file.patch            # applies the patch on file1
$ diff -u file1.txt file2.txt                     # verify that file1.txt was actually turned into file2.txt ./piff.py <file1> <file2>
```

## Patch Format

Piff uses custom patch format

- `action` `'A'` means add the `line` at the `row` index
- `action` `'R'` means remove the `line` at the `row` index

Here is an example of how it usually looks like:

```
A 4 Duis aute irure in dolor reprehenderit in voluptate velit
R 4 Duis aute irure dolor in reprehenderit in voluptate velit
A 7 asjdklaskldja
R 7 mollit anim id est laborum.
```

