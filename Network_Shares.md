### Network share comparisons.

| Microsoft Hosts | Linux Hosts |
|-----------------|-------------|
| Microsoft File and Print service | Network File System (NFS) daemon |
| Server Message Block (SMB) protocol | NFS protocol |

TCP 139 or 445
	

TCP and UDP 2049

Can support NFS with optional Server for NFS install
	

Can support SMB with optional Samba service install

Command to display all file servers on a network is net view
	

Command to display shares on a particular server is net view \\<server>
	

Command to display shares is showmount -e <target IP>

Command to connect to a particular share is net use \\server\share /u:<username> <password>
	

Command to connect to a particular share is mount -t nfs <target IP>:/share/subdirectory /local_directory
