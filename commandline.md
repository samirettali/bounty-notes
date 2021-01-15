# Command line

This is a reference to some useful commands that I always use
## Difference between two lists (must be sorted)

```
# Lines only in file1
$ comm -23 file1 file2 

# Lines only in file2
$ comm -13 file1 file2 

# Common lines
$ comm -12 file1 file2
```
