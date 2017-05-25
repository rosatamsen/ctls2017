## Looking at the Contents of Files

Everything we have seen so far has been with empty files and folders. We will now start looking at some real data. Navigate to your home directory, then issue the following `cp` command to copy a "tar archive" file from me:

```
$ cd ~     # the tilda ~ is also a shortcut referring to your home directory
$ pwd
/home/03439/wallen
$ cp /work/03439/wallen/public/IntroToLinuxHPC.tar .
```

Try to use `<Tab>` to autocomplete the name of the file. Also, please notice the single dot `.` at the end of the copy command, which indicates that you want to cp the tar archive to `.`, this present location (your home directory).

This archive file is actually a bundle of many files and folders, all packed into one nice, easily transportable object. Once it is copied over, un-pack the file with the following command:

```
$ ls
IntroToLinuxHPC.tar
$ tar -xvf IntroToLinuxHPC.tar
```

In the first lab (`Lab01`), we have a file called `websters.txt`. This a list of all the words in Webster's Dictionary. But how can we see the contents of the file?

```
$ cd IntroToLinuxHPC
$ cd Lab01
$ pwd
/home1/03439/wallen/IntroToLinuxHPC/Lab01
$ ls
README websters.txt
```

If you want to see the contents of a file, use the `cat` command to print it to screen:

```
$ cat websters.txt
A
a
aa
aal
aalii
aam
Aani
aardvark
...
```

This is a long file! Printing everything to screen is much too fast and not very useful. We can use a few other commands to look at the contents of the file with `more` control:

```
$ more websters.txt
```

Press the `<Enter>` key to scroll through line-by-line, or the `<Space>` key to scroll through page-by-page. Press `q` to quit the view, or `<Ctrl+c>` to force a quit if things freeze up. A `%` indicator at the bottom of the screen shows your progress through the file. This is still a little bit messy and fills up the screen. The `less` command has the same effect, but is a little bit cleaner:

```
$ less websters.txt
```

Scrolling through the data is the same, but now we can also search the data. Press the `/` forward slash key, and type a word that you would like to search for. The screen will jump down to the first match of that word. The `n` key will cycle through other matches, if they exist.

Finally, you can view just the beginning or the end of a file with the `head` and `tail` commands. For example:

```
$ head websters.txt
$ tail websters.txt
```

If you want to see more or fewer of the default 10 lines displayed, you can add a flag to the command. For example:

```
$ head -n 20 websters.txt
$ tail -n 1 websters.txt
```

Finally, the `>` and `>>` shortcuts in Linux indicate that you would like to redirect the output of one of the commands above. Instead of printing to screen, the output can be redirected into a file:

```
$ cat websters.txt > websters_new.txt
$ head -n 50 websters.txt > first_50_lines.txt
```

A single greater than sign `>` will redirect and **overwrite** any contents in the target file. A double greater than sign `>>` will redirect and **append** any output to the end of the target file.



## Review of Topics Covered:

| Command                     | Effect     |
|-----------------------------|------------|
| `cat file_name`             | print file contents to screen |
| `cat file_name >> new_file` | redirect output to new file |
| `more file_name`            | scroll through file contents |
| `less file_name`            | scroll through file contents |
| `head file_name`            | output beginning of file |
| `head -n 20 file_name`      | output first 20 lines of file |
| `tail file_name`            | output end of file |
| `tail -n 20 file_name`      | output last 20 lines of file |
| `~/`                        | shortcut for home directory |
| `<Ctrl+c>`                  | force interrupt |
| `>`                         | redirect and overwrite |
| `>>`                        | redirect and append |


Previous: [Creating and Manipulating Files](intro_to_linux_03.md) | Next: [More File Commands](intro_to_linux_05.md)
