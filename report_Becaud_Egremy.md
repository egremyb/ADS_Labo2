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
#### Manipulate the directories and files to obtain the following structure :
```
ex01_files
└── play
|   ├── trip
|   └── trip_copy
└── work
       └── book
           ├── chap01
           ├── chap02
           └── chap03
```
History of commands :
```
curl -O http://heigvd-ads.s3-website-eu-west-1.amazonaws.com/exercises/ex01_files.zip
unzip ex01_files.zip
cd ex01_files/
mv chap03 downloads/book/chap03
mv downloads/book/ work/
cp play/trip play/trip_copy
rmdir downloads/
```
Then we use the command `tree` to print the structure and get this :
```
.
├── play
│   ├── trip
│   └── trip_copy
└── work
       └── book
           ├── chap01
           ├── chap02
           └── chap03
```
#### Give the results without executing the commands
Given structure :
```
.
├── index2.html
├── index.html
├── index.html~
├── labs
│   ├── index.html
│   ├── lab01.html
│   └── starter.tar.gz
└── lectures
       └── index.html
```
Expected results of commands :  
- `mv labs/index.html labs.html`  
Move and rename `labs/index.html` as `labs.html` in current directory.  

- `mv labs labs.d`  
Rename `labs` directory as `labs.d`.

- `mv index2.html index.html`  
Rename `index2.html` with the same name as an existing file. The existing file is overwritten.

- `rm index.html~`  
Remove 'index.html~' file.

- `echo TBD > lectures/lc01.html`  
Create a new file and write `TBD` inside.

- `mkdir downloads`  
Create a directory named `downloads`.

- `cd downloads`  
Move in `downloads` directory.

- `mv ../labs/starter.tar.gz .`  
An error occured because the `labs` directory do not exist. It was renamed as `labs.d`.

Expected structure result :
```
ex02_files
├── downloads
├── index.html
├── labs.d
│   ├── lab01.html
│   └── starter.tar.gz
├── labs.html
└── lectures
       ├── index.html
       └── lc01.html
```

Result of `tree` after executing the commands :
```
.
├── downloads
├── index.html
├── labs.d
│   ├── lab01.html
│   └── starter.tar.gz
├── labs.html
└── lectures
       ├── index.html
       └── lc01.html
```

## Globbing
`ls` command list all the files in the current directory. It is possible to pipe his output for multiple purpose. One of them is for filtering.

#### Find all the logs of the first march 2015
All the given logs respond to a format. Dates can be found in files name.  
`2015-03-01T20_25_webserver.log` for example.

To list all the logs of the first march 2015, we can use this command :  
`ls | find -iname "2015-03-01*"`.

`find` command will any files respecting certains conditions. `-iname "abc*"` is a condition which a file name must begin with 'abc', replace 'abc' for what you are looking for.

#### Find all logs of the database's component
The database's component include the keyword `database` in their log's name.  
`2015-03-01T00_25_database.log` for example.

To list all the logs of the database's component, here is the command
`ls | find -iname "*database*"`

#### Find all logs of applications
The logs of applications include the keyword `app` in their log's name.
`2015-02-27T08_17_app_sales.log` for example.

To list all the logs of applications, here is the command
`ls | find -iname "*app*"`
