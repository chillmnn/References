# Kerberos

### Common Terminology  

<B>Ticket Granting Ticket (TGT)</B> - A ticket-granting ticket is an authentication ticket used to request service tickets from the TGS for specific resources from the domain.
<B>Key Distribution Center (KDC)</B> - The Key Distribution Center is a service for issuing TGTs and service tickets that consist of the Authentication Service and the Ticket Granting Service.
<B>Authentication Service (AS)</B> - The Authentication Service issues TGTs to be used by the TGS in the domain to request access to other machines and service tickets.
<B>Ticket Granting Service (TGS)</B> - The Ticket Granting Service takes the TGT and returns a ticket to a machine on the domain.
<B>Service Principal Name (SPN)</B> - A Service Principal Name is an identifier given to a service instance to associate a service instance with a domain service account. Windows requires that services have a domain service account which is why a service needs an SPN set.
<B>KDC Long Term Secret Key (KDC LT Key)</B> - The KDC key is based on the KRBTGT service account. It is used to encrypt the TGT and sign the PAC.
<B>Client Long Term Secret Key (Client LT Key)</B> - The client key is based on the computer or service account. It is used to check the encrypted timestamp and encrypt the session key.
<B>Service Long Term Secret Key (Service LT Key)</B> - The service key is based on the service account. It is used to encrypt the service portion of the service ticket and sign the PAC.
<B>Session Key</B> - Issued by the KDC when a TGT is issued. The user will provide the session key to the KDC along with the TGT when requesting a service ticket.
<B>Privilege Attribute Certificate (PAC)</B> - The PAC holds all of the user's relevant information, it is sent along with the TGT to the KDC to be signed by the Target LT Key and the KDC LT Key in order to validate the user.
