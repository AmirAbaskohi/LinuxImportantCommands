# File system and common Linux commands

## ls

`ls` stands for list which returns the list of files and directories in the current directory.

## cd

`cd` is used to change the directory. Using `cd` you can move through the file system.

`cd ..` moves you to the parent directory.
```
..: Parent Directory
.: Current Directory
```

### Main directories at root
```
bin: contains user executable files
boot: files required to boot the OS
dev: contains hardware devices that are connected to this machine(information about hardware devices)
etc: contains local system configuration files
home: home directory storage for user files
lib: library files that are required to boot the system
media: where we mount external media devices 
mnt: where mount temporarily file systems
opt: optional files
sbin: system binary files
tmp: temporary files(this folder can be deleted at a moment)
usr: sharable read-only files for all users
var: used by database softwares and data files
```

## clear

This commands clears the terminal.

## touch

`touch` command creates an empty files with the name specified.
```
touch filename
```

## pwd

`pwd` prints the current working directory.

## cat

`cat` can do multiple actions.

```
cat text.txt
```

prints the content of the `text.txt` file. This can be used to read a file.

You can write in a file using `cat` command as well:
```
cat text.txt >> newfile.txt
>>: means to put the output
```

or you can type using:
```
cat >> newfile.txt

using this command what you write in standard input(terminal) will be wrote in the file specified. You can end writing in standard input using Ctrl+D shortcut.
```
Remember that `cat` opens the file in append mode, which means what you writes does not override the content of the file.

When the file does not extend, `cat` creates the file for us.

In addition, you can concatenate of content of multiple files using `cat`:
```
cat file1.txt >> file2.txt
```

## mv

`mv` move files for you.
```
mv newfile.txt ./new_dir/newfile_in_newdir.txt
```

You can move multiple files as well:
```
mv file1.txt file2.txt ./new_dir/
```

## cp

`cp` copies a file for you.
```
mv newfile.txt ./new_dir/newfile_copy.txt
```

## rm
`rm` removes files.

```
rm file
```

Using `i` flag, gives you confirmation:
```
rm -i file
```

To remove empty directory use below command:
```
rm -d directory
```
If it is not empty use:
```
rm -r directory
```

In addition there is a `rmdir` command which removes empty directories.

## find

`find` will search for a specific file or directory in you current directory. You can declare another directory as well:
```
find directory_to_search -name name_of_what_we_want_to_search
```

Using `iname` instead of `name` does not consider capital. 

To look for directories use below command:
```
find directory_to_search type d -name name_of_what_we_want_to_search
```