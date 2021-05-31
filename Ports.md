### Ports

| Port     | Service |
| ----------- | ----------- |
| 20 /TCP, UDP | FTP data |
| 21 /TCP, UDP | FTP control |
| 22 /TCP, UDP | SSH |
| 23 /TCP, UDP | Telnet |
| 25 /TCP, UDP | SMTP |
| 53 /UDP | DNS |
| 67 /TCP, UDP | DHCP server |
| 68 /TCP, UDP | DHCP client |
| 69 /TCP, UDP | TFTP |
| 80 /TCP, UDP | HTTP |
| 88 /TCP, UDP | Kerberos |
| 110 /TCP, UDP | POP3 |
| 123 /TCP, UDP | NTP |
| 135 /TCP, UDP | Microsoft EPMAP/RPC |
| 136-139 /TCP, UDP | NetBIOS |
| 143 /TCP | IMAP |
| 161 /UDP | SNMP |
| 162 /TCP, UDP | SNMP traps |
| 389 /TCP, UDP | LDAP |
| 443 /TCP, UDP | HTTPS |
| 445 /TCP | Microsoft AD and SMB |
| 500 /TCP, UDP | ISAKMP, IKE |
| 515 /TCP | LPD print services |
| 902 /TCP | VMware Server |
| 1433 /TCP | MSSQL |
| 1434 /TCP, UDP | Microsoft SQL Monitor |
| 1521 /TCP | Oracle database listener |
| 1812, 1813 /TCP, UDP | RADIUS |
| 2049 /TCP | NFS |
| 3306 /TCP | MySQL |
| 3389 /TCP | RDP |

### Common ports and tools used for enumeration.
| Port | Protocol and Service | Tool Examples | Comments |
|------|----------------------|---------------|----------|
| TCP 21 | FTP FTP file server | Telnet & FTP clients, nmap ftp-anon.nse, ftp-brute.nse, Metasploit modules: ftp/anonymous, ftp_login, ftp_version. | Identify FTP servers, versions, and authentication requirements (including anonymous logins). |
| TCP 22 | SSH SSH server | nmap, PuTTY/SSH clients, nmap ssh-brute.nse, ssh-run.nse, Metasploit modules: ssh_login, ssh_login_pubkey. | Linux servers, routers, switches, other network devices, jailbroken iPhones. |

TCP 23
	

telnet

Telnet server
	

PuTTY/telnet clients, nmap telnet-brute.nse, telnet-ntlm-info.nse, Metasploit telnet_login, telnet_version modules.
	

Linux servers, routers, switches, other network devices.

TCP 25
	

SMTP

Email server
	

PuTTY/telnet clients, nmap smtp-enum-users.nse, smtp-commands.nse, smtp-open-relay.nse, smtp-brute.nse, Metasploit smtp_enum, smtp_version modules.
	

Extract email addresses. Enumerate SMTP server information. Search for open relays.

TCP 53
	

DNS

DNS
	

dig, nslookup, nmap dns-brute.nse, Metasploit enum_dns module.
	

Elicit DNS zone transfers. Discover DNS subdomains.

TCP 80
	

HTTP

Web server
	

PuTTY/telnet clients, dirbuster, nmap http-enum.nse, http-title.nse, http-sitemap-generator.nse, Metasploit modules: http_cert, dir_listing, dir_scanner, dir_webdav_unicode_bypass,enum_wayback, files_dir, http_login, http/ssl, http_version, webdav_scanner, webdav_website_content.
	

Manually request web pages, enumerate directories, files, WebDAV features, versions, and more.

TCP 135, TCP 111
	

RPC

Microsoft DCE/RPC Locator Service, *nix portmapper service
	

nmap rpcinfo.nse, rpc-grind.nse, msrpc-enum.nse, Metasploit dcerpc modules: endpoint_mapper, hidden, management, tcp_dcerpc_auditor.
	

Query and manipulate Remote Procedure Call (RPC)-based services such as Windows DCOM, and *nix NFS, nlockmgr, quotad, and mountd.

TCP 137
	

NetBIOS

NetBIOS Name Service
	

nbtscan, nmap smb-enum-shares.nse, smb-enumdomains.nse, smb-os-discovery.nse.
	

List NetBIOS computer, user, group, workgroup, and domain names, domain controller roles, file and print sharing services, Microsoft Exchange services.

TCP 139
	

SMB

NetBIOS Session Service (SMB file and print service)
	

enum.exe (Windows), enum4linux.pl, smbclient, nmap smb-enum-shares.nse, smb-os-discovery.nse, Metasploit modules: smb_enumshares, smb/smb2, smb_version.
	

Retrieve directory information, list and transfer files. NSE scripts might not work on newer machines.

UDP 161
	

SNMP

SNMP
	

getif, SolarWinds NPM, PRTG, WhatsUp Gold, Nagios Core, Spiceworks, Observium, nmap snmp-info.nse, snmp-brute.nse, snmp-interfaces.nse, snmp-processes.nse, Metasploit snmp modules: snmp_enum, snmp_enumusers, snmp_enumshares, snmp_login.
	

Obtain information on dozens of data objects depending on device. Targets must have SNMP agent enabled; you must know the community string devices are using (can be sniffed).

TCP/UDP 389
	

LDAP

Microsoft Active Directory
	

Active Directory Users and Computers, ntdsutil.exe, OpenLDAP, LDAP Admin, LDP.exe, nmap ldap-search.nse, Metasploit module: enum_ad_computers.
	

Retrieve a wide range of information from Active Directory. Non-privileged users can query Active Directory for nearly all information. To capture password hashes, copy the database file ntds.dit using ntdsutil.exe, then use Windows Password Recovery Tool to extract the hashes.

TCP 445
	

RPC

Microsoft-DS Active Directory and SMB file sharing
	

rpcclient, Metasploit smb_login, smb_enumusers, & smb/psexec modules, nmap NSE smb-enum-* scripts, enum.exe, user2sid.exe, sid2user.exe, PowerShell, pstools.
	

Retrieve a very wide range of Microsoft computer and domain information.

TCP 1433
	

SQL

SQL Server
	

nmap mysql-info.nse, Metasploit modules: mssql_ping, mssql_enum, enum_domain_accounts, enum_sql_logins.
	

Locate and enumerate information including logins from Microsoft and MySQL SQL servers. 
