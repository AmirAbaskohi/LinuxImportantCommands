# Users and Groups

## Adding new user

To add new use you can use below command:
```
adduser new_user
```

After running the above command, you can see that it will creates bunch of different things for you:
* It adds new user
* It adds new group
* It adds new user with the created group
* It creates a home directory for the new user
* It copies files from `/etc/skel` which is the skeleton of the new user

After this, you will be asked to enter the password for the new user. Then you will be asked to enter some optional additionl information like full name, room number, work phone, etc. In the end you should confirm the information.

## See all the users in the system

To see all users in the system you can use the following command:
```
cat /etc/passwd
```

There are a lot of different users. They exist to make sure that applications and processes have the correct permissions and everything runs properly.

## Sign in as other users

To logout of a user you can use the following command:
```
logout
```

After logout, you can enter as other users by giving the username and password to the system.

## Deleting a user
```
deluser username
```

## Update password
```
passwd username
```

Using the following command will change the password of the current user:
```
passwd
```

## What are groups?

In Linux, a group is a collection of users. The main purpose of the groups is to define a set of privileges like read, write, or execute permission for a given resource that can be shared among the users within the group.

## Adding a group
```
addgroup groupname
```

## Assigning users to groups
```
usermod -a -G groupname username
```

## Seeing the groups of a user
```
groups username
```

## Remove user from group
```
gpass -d username groupname
```

## Editing group permissions
All of the permissions for groups are stored in what's known as sudo vars file. 

To access this file, first of all the user has to be granted to do so. To open the file you can use the following command:
```
nano visudo
```

Instead of `nano` you can use whatever editor you like.

To give a user some permissions, find `# User privilege specification` comment in the `visudo` file and give the permission to the user like this:
```
username    ALL=adress_to_first_command,adress_to_second_command,...
```

To give groups some permission use add the following line after `# Allow members of group sudo to execute any command` comment:
```
%groupname ALL=adress_to_first_command,adress_to_second_command,...
```

## Finding command location
```
which command_name
```

## Delete a group
```
delgroup groupname
```