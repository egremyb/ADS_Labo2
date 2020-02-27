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
#### What are the nine sections of Unix manual ?
By using the command `man man`, the sections are :
1. Executable programs or shell commands
1. System calls (functions provided by the kernel)
1. Library calls (functions within program libraries)
1. Special files (usually found in /dev)
1. File formats and conventions eg /etc/passwd
1. Games
1. Miscellaneous (including macro packages and conventions), e.g. man(7), groff(7)
1. System administration commands (usually only for root)
1. Kernel routines [Non standard]

But [Wikipedia](https://en.wikipedia.org/wiki/Man_page) gives us more informations :

1. Users commands
1. System calls
1. Library functions, __covering in particular the C standard library__
1. Special files (usually devices, those found in /dev) __and drivers__
1. File formats and conventions
1. Games __and screensavers__
1. Miscellanea
1. System administration commands __and daemons__
1. Linux kernel interface

#### Which section of Unix manual contains `cat`and `ls` commands ?
Those commands are contained in the first section `User commands`.

#### Which section document files format such as configuration files ?
As the name suggest, files format's documentation is stored in the fifth section `File Formats and conventions`.

#### Which section contains system administration commands such as `shutdown` ?
System administration commands are documented in the eighth section.

## Structure of _man pages_

### Synopsis section

### Other sections

### Resolve ambiguity

### `ls` command

## Absolute and relative path
#### Absolute path
Absolute path points to a specific file or directory location from the root directory `/`.

Absolute path to ssh : `/usr/bin/ssh`

#### Relative path
Relative path points to a specific file or directory like an absolute path but it does not begin from the root directory.

Here are `relative paths` to ssh from their current directory.
1. /usr/`bin/ssh`
1. /usr/bin/`ssh`
1. /usr/share`/../bin/ssh`
1. /usr/local/bin`/../../bin/ssh`

## File handling

## Globbing
