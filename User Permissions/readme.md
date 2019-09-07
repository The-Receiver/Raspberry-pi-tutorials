# Managing account permissions on Linux


This tutorial will assume 4 users: 
-pi, who will be able to see all files
-teacher, who will be able to see student's files but not edit them
-student1, who will only be able to see, write and run his own files.
-student2, who will only be able to see, write and execute his own files.

## Creating a user 

To create a user called student1, we can run one commands:
``` sudo adduser student1 ```


## Adding user to a group

We can run the command ```cd /home && ls``` in the terminal to show the folders of all users on the pi.


## Chmod

The command ```chmod``` is used to edit permissions on linux.

On linux there are three types of permissions:
r(ead) - Users with read access can see files but cannot run them.
w(rite) - Users with write access can change files.
e(x)ecute - Users with execute access can run the file.



chmod files have this syntax:

<name of file or folder>

## Access Control Lists with 
