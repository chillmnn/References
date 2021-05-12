# CHMOD

Permissions are divided into three sections. User, Groups, Everyone Else.
| RWX | RWX | RWX |
|-----|-----|-----|
|  U |  G |  EE |

Digits that control read, write or execute for each user, group or everyone else.
| Digit | Meaning |
|-------|---------|
| 1 |	File can be executed |
| 2	| File can be written to |
| 3 | File can be executed and written to |
| 4 | File can be read |
| 5 | File can be read and executed |
| 6 | File can be written to and read |
| 7 | File can be read, written to, and executed |

Example usage: ``` chmod 431 <file> ```
* 4 User can read the file.
* 3 Group can execute and read the file.
* 1 Everyone else can execute the file.
