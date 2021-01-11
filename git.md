# Git

## Dump objects
This command try to get as much content as possible from the objects in the
repository, useful for example when you get a partial exposed repository:
```
$ git cat-file --batch --batch-all-objects
```

More elaborate version:
```
$ mkdir output
$ git cat-file --batch-check --batch-all-objects | cut -d " " -f1 | \
    while read line; do git cat-file -p $line > ./output/$line.file; done
```
