# ADS Laboratoire 02

## Pagination tool `less`

1. **Which key is used to reach the start of the file ?**

  `g`

2. **Which key is used to reach the end of the file ?**

  `G`

3. **How can you search for the pattern _admin_ ?**

  `/admin`

4. **How do you go to the next occurrence ?**

  `/`

5. **What is the effect of adding _-i_ before the search ? And _-i_ repeatedly ? Starting at the beginning of the file, search for the pattern _bob_.**

  Adding _-i_ make the search case insensitive. By adding it multiple times, it acts like a switch and change the sensitivity to the case each time.

6. **What happen if you open :**

  1. **A compressed file like `/usr/share/doc/bash/INTRO.gz` ?**

    A message tells us that the file might be a binary one and then asks us if we want to see it anyway. In that case, it proceeds to display the content of the file into ASCII characters that doesn't make understandable sentences (a lot of non-alphabetical characters might be displayed). The content of the file isn't understandable for a human in this state.

  2. **A compressed archive like `/usr/share/doc/apg/php.tar.gz` ?**

    Same as the previous answer.

## Navigation into the Unix manual

### What are the nine sections of Unix manual ?

By using the command `man man`, the sections are :

1. Executable programs or shell commands
2. System calls (functions provided by the kernel)
3. Library calls (functions within program libraries)
4. Special files (usually found in /dev)
5. File formats and conventions eg /etc/passwd
6. Games
7. Miscellaneous (including macro packages and conventions), e.g. man(7), groff(7)
8. System administration commands (usually only for root)
9. Kernel routines [Non standard]

But [Wikipedia](https://en.wikipedia.org/wiki/Man_page) gives us more informations :

1. Users commands
2. System calls
3. Library functions, **covering in particular the C standard library**
4. Special files (usually devices, those found in /dev) **and drivers**
5. File formats and conventions
6. Games **and screensavers**
7. Miscellanea
8. System administration commands **and daemons**
9. Linux kernel interface

### Which section of Unix manual contains `cat`and `ls` commands ?

Those commands are contained in the first section `User commands`.

### Which section document files format such as configuration files ?

As the name suggest, files format's documentation is stored in the fifth section `File Formats and conventions`.

### Which section contains system administration commands such as `shutdown` ?

System administration commands are documented in the eighth section.

## Structure of _man pages_
### Synopsis section

```
mkpasswd PASSWORD SALT
```
`PASSWORD` and `SALT` are 2 required arguments which need to be put in this specific order.

```
uniq uniq [OPTION] ... [INPUT [OUTPUT]]
```
`[OPTION]`and `[INPUT]` are optional arguments. There can be as many as wanted from the *OPTION* or *INPUT* section respectively. `OUTPUT` is optional but can only be used when `[INPUT]` is used. As the other ones, any argument from the *OUTPUT* section can be used.

```
gzip [ -acdfhlLnNrtvV19 ] [-S suffix] [ name ... ]
```
`[ -acdfhlLnNrtvV19 ]` are optional and any number of the specified argument can be used but it has to be listed in the synopsis.
`[-S suffix]` is a single optional argument.
`[ name ... ]` are optional *names* that can be passed as arguments.

### Other sections

### Resolve ambiguity

### `ls` command

## Absolute and relative path

## File handling

## Globbing
