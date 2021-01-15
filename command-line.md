# Command line

## moreutils

`moreutils` is a collection of great command line tools that allows me to write
my recon automated scripts in a really clean way, without using ugly hacks like
temporary files.

## Merge two lists (does not remove duplicates)

```
$ combine domains.txt or newdomains.txt
```

## Sort and filter a list in place

```
$ cat domains.txt | sort -u | grep -v filter | sponge domains.txt
```

## Print lines that are in both files

```
$ combine domains.txt and newdomains.txt
```

## Print lines that are only in `newdomains.txt`

```
$ combine newdomains.txt not domains.txt
```

## Get lines that are only in one of the two files

```
$ combine file1.txt xor file2.txt
```

## Filter new domains from a command

```
$ subfinder -d example.com | combine - not domains.txt > newdomains.txt
```

## Get notified about new domains

Let's say you have a script that automates some recon steps, and a script called `notify.sh` that notifies you on slack or discord if new domains are found or something else.

You can use `combine` to filter new domains, `tee` to write them to a file and pipe them to `ifne` that runs the specified command (`./notify.sh` in this case) only if it the output of the previous command wasn't empty, i.e. there are new domains:

```
$ subfinder -d example.com | combine - not domains.txt | tee -a new.txt | ifne ./notify.sh
```

## Manually filter domains between pipes

Let's say you want to run you usual recon routine, but before dns resolution you want to filter out some domains manually.

Just pipe the domains in `vipe`, it will open them in your editor, allowing you do filter the one you want and pass them along:

```
$ subfinder -d example.com | vipe | dnsx | httpx -title -status-code
```
