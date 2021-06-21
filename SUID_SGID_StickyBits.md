| Permission  | On Files  | On Directories  |
| ----------- | --------- | --------------- |
| SUID Bit  |	User executes the file with permissions of the file owner.  |  |
| SGID Bit  |	User executes the file with the permission of the group owner.  | File created in directory gets the same group owner.  |
| Sticky Bit  |	  | No meaning	Users are prevented from deleting files from other users. |

### To search the system for these types of files run:
```find / -perm -u=s -type f 2>/dev/null```

### Find all SUID/SGID executibles on Debian.
```find / -type f -a \( -perm -u+s -o -perm -g+s \) -exec ls -l {} \; 2> /dev/null```
