# File permission and chmod

## Detailed information of files
```
ls -l
```

The result of the following command is a list of items like this:
```
-rw-r--r-- 1 root root 4096 Jan 5 22:38 newfile.txt
```

`-rw-r--r--` shows the file's permissions. The next one shows the number of files contained in this file. For files this values will be 1, but it can be different for directories. Then next one which is `root` shows the file owner. Then next one shows the group that owns this file which is `root` in this case. Then we have the size of file. Then we have time and date that this file has been created. In the end we have the file name.

Now lets see what information we can get from a permission string:
```
drwxr-xr-x

The first character can be one of these things:
- d: directory
- -: regular file
- l: link

The next characters represents the permission of this file. These nine characters should be read in three sets of three characters.

- rwx
- r-x
- r-x

The first set is permission for the user. The second set is the permission for the group and the third group is the permission for all users.

r shows read, w shows write and x is for execute.

```

## Changing the permission of a file

As a creator or owner of a file, you change the permission of a file using the following command:
```
chmod [u(user)/g(group)/o(other)/a(all)] [+(add),-(remove),=(set)] [permission(s)] filename
```

Here are some examples:
```
chmod a+w file.txt  : All users can write
chmod u+x file.txt : The current user can execute the file
chmod -R a+w directory : -R shows this should happen recursively
chmod -R a-w directory : Removing writing permission for the directory
chmod -R a=w directory : All users can just write in the directory
```

If you do not specify who we want the command for, by default the permission change will happen for all of the users.

To set multiple permissions, you can separate them by comma like this:
```
chmod g+2,o-rw,a+x file.txt
```