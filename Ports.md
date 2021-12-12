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
| TCP 23 | telnet Telnet server | PuTTY/telnet clients, nmap telnet-brute.nse, telnet-ntlm-info.nse, Metasploit telnet_login, telnet_version modules. | Linux servers, routers, switches, other network devices. |
| TCP 25 | SMTP Email server | PuTTY/telnet clients, nmap smtp-enum-users.nse, smtp-commands.nse, smtp-open-relay.nse, smtp-brute.nse, Metasploit smtp_enum, smtp_version modules. | Extract email addresses. Enumerate SMTP server information. Search for open relays. |
| TCP 53 | DNS | dig, nslookup, nmap dns-brute.nse, Metasploit enum_dns module. | Elicit DNS zone transfers. Discover DNS subdomains. |
| TCP 80 | HTTP Web server | PuTTY/telnet clients, dirbuster, nmap http-enum.nse, http-title.nse, http-sitemap-generator.nse, Metasploit modules: http_cert, dir_listing, dir_scanner, dir_webdav_unicode_bypass,enum_wayback, files_dir, http_login, http/ssl, http_version, webdav_scanner, webdav_website_content. | Manually request web pages, enumerate directories, files, WebDAV features, versions, and more. |
| TCP 135, TCP 111 | RPC Microsoft DCE/RPC Locator Service, Liniux portmapper service | nmap rpcinfo.nse, rpc-grind.nse, msrpc-enum.nse, Metasploit dcerpc modules: endpoint_mapper, hidden, management, tcp_dcerpc_auditor. | Query and manipulate Remote Procedure Call (RPC)-based services such as Windows DCOM, and Linux NFS, nlockmgr, quotad, and mountd. |
| TCP 137 | NetBIOS NetBIOS Name Service | nbtscan, nmap smb-enum-shares.nse, smb-enumdomains.nse, smb-os-discovery.nse. | List NetBIOS computer, user, group, workgroup, and domain names, domain controller roles, file and print sharing services, Microsoft Exchange services. |
| TCP 139 | SMB NetBIOS Session Service (SMB file and print service) | enum.exe (Windows), enum4linux.pl, smbclient, nmap smb-enum-shares.nse, smb-os-discovery.nse, Metasploit modules: smb_enumshares, smb/smb2, smb_version. | Retrieve directory information, list and transfer files. NSE scripts might not work on newer machines. |
| UDP 161 | SNMP | getif, SolarWinds NPM, PRTG, WhatsUp Gold, Nagios Core, Spiceworks, Observium, nmap snmp-info.nse, snmp-brute.nse, snmp-interfaces.nse, snmp-processes.nse, Metasploit snmp modules: snmp_enum, snmp_enumusers, snmp_enumshares, snmp_login. | Obtain information on dozens of data objects depending on device. Targets must have SNMP agent enabled; you must know the community string devices are using (can be sniffed). |
| TCP/UDP 389 | LDAP Microsoft Active Directory | Active Directory Users and Computers, ntdsutil.exe, OpenLDAP, LDAP Admin, LDP.exe, nmap ldap-search.nse, Metasploit module: enum_ad_computers. | Retrieve a wide range of information from Active Directory. Non-privileged users can query Active Directory for nearly all information. To capture password hashes, copy the database file ntds.dit using ntdsutil.exe, then use Windows Password Recovery Tool to extract the hashes. |
| TCP 445 | RPC Microsoft-DS Active Directory and SMB file sharing | rpcclient, Metasploit smb_login, smb_enumusers, & smb/psexec modules, nmap NSE smb-enum-* scripts, enum.exe, user2sid.exe, sid2user.exe, PowerShell, pstools. | Retrieve a very wide range of Microsoft computer and domain information. |
| TCP 1433 | SQL Server | nmap mysql-info.nse, Metasploit modules: mssql_ping, mssql_enum, enum_domain_accounts, enum_sql_logins. | Locate and enumerate information including logins from Microsoft and MySQL SQL servers. |

# Control Systems Ports

## Standard Protocol Ports

The standard protocol ports table lists the ports for protocols that are considered industry standards and are used be multiple vendors.

| Protocol                |                 Ports                  |
| ----------------------- | :------------------------------------: |
| BACnet/IP               |               UDP/47808                |
| DNP3                    |          TCP/20000, UDP/20000          |
| EtherCAT                |               UDP/34980                |
| Ethernet/IP             |     TCP/44818, UDP/2222, UDP/44818     |
| FL-net                  |           UDP/55000 to 55003           |
| Foundation Fieldbus HSE |   TCP/1089 to 1091, UDP/1089 to 1091   |
| ICCP                    |                TCP/102                 |
| Modbus TCP              |                TCP/502                 |
| OPC UA Binary           |      Vendor Application Specific       |
| OPC UA Discovery Server |                TCP/4840                |
| OPC UA XML              |            TCP/80, TCP/443             |
| PROFINET                | TCP/34962 to 34964, UDP/34962 to 34964 |
| ROC PLus                |              TCP/UDP 4000              |

## Vendor Specific Ports

The vendor specific ports tables lists ports that are used by only one or a small number of vendors. These protocols are usually unpublished and proprietary.

| Vendor           |    Product or Protocol    |                                                                                                                                                                             Ports                                                                                                                                                                             |
| ---------------- | :-----------------------: | :-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| ABB              |        Ranger 2003        |                  TCP/10307, TCP/10311, TCP/10364 to 10365, TCP/10407, TCP/10409 to 10410, TCP/10412, TCP/10414 to 10415, TCP/10428, TCP/10431 to 10432, TCP/10447, TCP/10449 to 10450, TCP/12316, TCP/12645, TCP/12647 to 12648, TCP/13722, TCP/13724, TCP/13782 to 13783, TCP/38589, TCP/38593, TCP/38600, TCP/38971, TCP/39129, TCP/39278                   |
| Emerson / Fisher |         ROC Plus          |                                                                                                                                                                         TCP/UDP/4000                                                                                                                                                                          |
| Foxboro/Invensys |    Foxboro DCS FoxApi     |                                                                                                                                                                         TCP/UDP/55555                                                                                                                                                                         |
| Foxboro/Invensys |    Foxboro DCS AIMAPI     |                                                                                                                                                                         TCP/UDP/45678                                                                                                                                                                         |
| Foxboro/Invensys |   Foxboro DCS Informix    |                                                                                                                                                                         TCP/UDP/1541                                                                                                                                                                          |
| Iconics          | Genesis32 GenBroker (TCP) |                                                                                                                                                                           TCP/18000                                                                                                                                                                           |
| Johnson Controls |        Metasys N1         |                                                                                                                                                                         TCP/UDP/11001                                                                                                                                                                         |
| Johnson Controls |      Metasys BACNet       |                                                                                                                                                                           UDP/47808                                                                                                                                                                           |
| OSIsoft          |         PI Server         |                                                                                                                                                                           TCP/5450                                                                                                                                                                            |
| Siemens          |     Spectrum Power TG     |                                                                                                                              TCP/50001 to 50016, TCP/50018 to 50020, UDP/50020 to 50021, TCP/50025 to 50028, TCP/50110 to 50111                                                                                                                               |
| SNC              |           GENe            | TCP/38000 to 38001, TCP/38011 to 38012, TCP/38014 to 38015, TCP/38200, TCP/38210, TCP/38301, TCP/38400, TCP/38700, TCP/62900, TCP/62911, TCP/62924, TCP/62930, TCP/62938, TCP/62956 to 62957, TCP/62963, TCP/62981 to 62982, TCP/62985, TCP/62992, TCP/63012, TCP/63027 to 63036, TCP/63041, TCP/63075, TCP/63079, TCP/63082, TCP/63088, TCP/63094, TCP/65443 |
| Telvent          |         OASyS DNA         |                                                                                                                                         UDP/5050 to 5051, TCP/5052, TCP/5065, TCP/12135 to 12137, TCP/56001 to 56099                                                                                                                                          |
| OMRON          |         FINS communication protocol         |                                                                                                                                                                           TCP/UDP/9600

## All Control System Ports Sorted By Port Number

The control system ports table combines the previous two tables and sorts the entries by port number.

| Protocol           |                 Ports                 |
| ------------------ | :-----------------------------------: |
| TCP/502            |              Modbus TCP               |
| TCP/UDP/1089       |        Foundation Fieldbus HSE        |
| TCP/UDP/1090       |        Foundation Fieldbus HSE        |
| TCP/UDP/1091       |        Foundation Fieldbus HSE        |
| TCP/UDP/1541       | Foxboro/Invensys Foxboro DCS Informix |
| UDP/2222           |              EtherNet/IP              |
| TCP/3480           |        OPC UA Discovery Server        |
| TCP/UDP/4000       |        Emerson/Fisher ROC Plus        |
| UDP/5050 to 5051   |           Telvent OASyS DNA           |
| TCP/5052           |           Telvent OASyS DNA           |
| TCP/5065           |           Telvent OASyS DNA           |
| TCP/5450           |           OSIsoft PI Server           |
| TCP/UDP/9600       |           OMRON FINS protocol         |    
| TCP/10307          |            ABB Ranger 2003            |
| TCP/10311          |            ABB Ranger 2003            |
| TCP/10364 to 10365 |            ABB Ranger 2003            |
| TCP/10407          |            ABB Ranger 2003            |
| TCP/10409 to 10410 |            ABB Ranger 2003            |
| TCP/10412          |            ABB Ranger 2003            |
| TCP/10414 to 10415 |            ABB Ranger 2003            |
| TCP/10428          |            ABB Ranger 2003            |
| TCP/10431 to 10432 |            ABB Ranger 2003            |
| TCP/10447          |            ABB Ranger 2003            |
| TCP/10449 to 10450 |            ABB Ranger 2003            |
| TCP/12316          |            ABB Ranger 2003            |
| TCP/12645          |            ABB Ranger 2003            |
| TCP/12647 to 12648 |            ABB Ranger 2003            |
| TCP/13722          |            ABB Ranger 2003            |
| TCP/UDP/11001      |      Johnson Controls Metasys N1      |
| TCP/12135 to 12137 |           Telvent OASyS DNA           |
| TCP/13724          |            ABB Ranger 2003            |
| TCP/13782 to 13783 |            ABB Ranger 2003            |
| TCP/18000          |   Iconic Genesis32 GenBroker (TCP)    |
| TCP/UDP/20000      |                 DNP3                  |
| TCP/UDP/34962      |               PROFINET                |
| TCP/UDP/34963      |               PROFINET                |
| TCP/UDP/34964      |               PROFINET                |
| UDP/34980          |               EtherCAT                |
| TCP/38589          |            ABB Ranger 2003            |
| TCP/38593          |            ABB Ranger 2003            |
| TCP/38000 to 38001 |               SNC GENe                |
| TCP/38011 to 38012 |               SNC GENe                |
| TCP/38014 to 38015 |               SNC GENe                |
| TCP/38200          |               SNC GENe                |
| TCP/38210          |               SNC GENe                |
| TCP/38301          |               SNC GENe                |
| TCP/38400          |               SNC GENe                |
| TCP/38600          |            ABB Ranger 2003            |
| TCP/38700          |               SNC GENe                |
| TCP/38971          |            ABB Ranger 2003            |
| TCP/39129          |            ABB Ranger 2003            |
| TCP/39278          |            ABB Ranger 2003            |
| TCP/UDP/44818      |              EtherNet/IP              |
| TCP/UDP/45678      |  Foxboro/Invensys Foxboro DCS AIMAPI  |
| UDP/47808          |               BACnet/IP               |
| TCP/50001 to 50016 |       Siemens Spectrum Power TG       |
| TCP/50018 to 50020 |       Siemens Spectrum Power TG       |
| UDP/50020 to 50021 |       Siemens Spectrum Power TG       |
| TCP/50025 to 50028 |       Siemens Spectrum Power TG       |
| TCP/50110 to 50111 |       Siemens Spectrum Power TG       |
| UDP/55000 to 55002 |           FL-net Reception            |
| UDP/55003          |          FL-net Transmission          |
| TCP/UDP/55555      |  Foxboor/Invensys Foxboro DCS FoxAPI  |
| TCP/56001 to 56099 |           Telvent OASyS DNA           |
| TCP/62900          |               SNC GENe                |
| TCP/62911          |               SNC GENe                |
| TCP/62924          |               SNC GENe                |
| TCP/62930          |               SNC GENe                |
| TCP/62938          |               SNC GENe                |
| TCP/62956 to 62957 |               SNC GENe                |
| TCP/62963          |               SNC GENe                |
| TCP/62981 to 62982 |               SNC GENe                |
| TCP/62985          |               SNC GENe                |
| TCP/62992          |               SNC GENe                |
| TCP/63012          |               SNC GENe                |
| TCP/63027 to 63036 |               SNC GENe                |
| TCP/63041          |               SNC GENe                |
| TCP/63075          |               SNC GENe                |
| TCP/63079          |               SNC GENe                |
| TCP/63082          |               SNC GENe                |
| TCP/63088          |               SNC GENe                |
| TCP/63094          |               SNC GENe                |
| TCP/65443          |               SNC GENe                |
