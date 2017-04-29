# letsencrypt_certbot_standalone_icecast
Using Letsencrypt Certbot package to create certs for icecast

These steps were used to create and renew a Let's Encrypt certificate on a CentOS 7.x server.
Installed software includes: Icecast v2.4.2 and Liquidsoap 1.3.0
There is NO nginx or apache loaded


Use the installnewcert file to create your new script
Use the renewcert file to copy the new script to your existing icecast and backup original production cert.

Note: read the notes in each file to be sure you modify to suit your needs.



Background: Using the certbot with the commands in the installnewcert file you will not need to install nginx or apache or add any DNS records to create the certification.  You must have the proper A/CNAME record to map the domain name to the server you are running this on.

The basic steps for this are to enable 443 on your firewall, create the cert through let's encrypt, disable 443 on firewall, copy the cert from the default let's encrypt folder to your icecast cert folder and backup the original icecast cert.  Then stop and start icecast services.  It is recommended that you create a crontab entry weekly or monthly for the renewcert file.
