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
r(ead) - Users with read access to a file or folder can see it but cannot run it.
w(rite) - Users with write access to a file can change the file. 
e(x)ecute - Users with execute to a file can change the file. 


chmod files have this syntax:

chmod -<g/o/u/a><+/-><r/w/x> <name of file or folder>  
  guoa are three different targets for chmod. g targets the group of the folder, o people not part of the group, u the user who owns the file, and a, everyone on the system.
  rwx are the three different permissions. If we put a + behind the letters, it will add the permission to the targets. If we put a - behind the letters, it will take away those permissions.
  
To test this, we first ``` cd /home``` so we can act on all files.

Now we can simply run
``` chmod o-rwx student1``` to take away read, write and execute abilitity for everyone other than student1.


## Access Control Lists with 
So far, chmod can only deny permissions to everybody, nobody, or one group. But we want to specify the permissions of manyu different groups. To do this we install acl, and run the command facl. To learn more about this command, type ``` man facl ```.
``` sudo apt install acl ```

This command acts on the group readers, then adds write and execute ability. It acts on the folder student1.
```sudo setfacl -m g:readers:rx -R /student1```






