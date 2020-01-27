
```
PS C:\maverick\certificates> ls
PS C:\maverick\certificates> set RANDFILE:\maverick\certificates\.rnd
PS C:\maverick\certificates> pwd

PS C:\maverick> cd .\OpenSSL-Win64\
PS C:\maverick\OpenSSL-Win64> ls


    Directory: C:\maverick\OpenSSL-Win64


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        4/15/2019  10:40 AM                bin
d-----        4/15/2019  10:40 AM                exp
d-----        4/15/2019  10:40 AM                include
d-----        4/15/2019  10:40 AM                lib
-a----        2/26/2019   6:20 AM         507893 changes.txt
-a----         5/3/2016   6:38 AM             84 faq.txt
-a----        2/26/2019   6:10 PM        2096128 libeay32.dll
-a----        2/26/2019   6:11 PM         353792 libssl32.dll
-a----        2/26/2019   6:20 AM           6281 license.txt
-a----        2/26/2019   6:20 AM          35823 news.txt
-a----        2/26/2019   6:20 AM           3282 readme.txt
-a----        2/26/2019   6:11 PM         353792 ssleay32.dll
-a----        4/15/2019  10:40 AM          22395 unins000.dat
-a----        4/15/2019  10:39 AM         730789 unins000.exe

PS C:\maverick\OpenSSL-Win64> cd ..


    Directory: C:\maverick


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        4/15/2019  10:48 AM                certificates
d-----        4/15/2019  10:40 AM                OpenSSL-Win64

```

## Generating a Certificate
```
PS C:\maverick> cd certificates
PS C:\maverick\certificates> C:\maverick\OpenSSL-Win64\bin\openssl.exe
OpenSSL> genrsa -out client.key 2048
Generating RSA private key, 2048 bit long modulus
.............+++++
..................................................+++++
e is 65537 (0x10001)
OpenSSL> req -key client.key -new -out client.req
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields there will be a default value,
If you enter '.', the field will be left blank.
-----
Country Name (2 letter code) [AU]:US
State or Province Name (full name) [Some-State]:Indiana
Locality Name (eg, city) []:West Lafayette
Organization Name (eg, company) [Internet Widgits Pty Ltd]:OATS
Organizational Unit Name (eg, section) []:problems making Certificate Request
PS C:\maverick\certificates> C:\maverick\OpenSSL-Win64\bin\openssl.exe
OpenSSL> req -key client.key -new -out client.req
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields there will be a default value,
If you enter '.', the field will be left blank.
-----
Country Name (2 letter code) [AU]:US
State or Province Name (full name) [Some-State]:Indiana
Locality Name (eg, city) []:West Lafayette
Organization Name (eg, company) [Internet Widgits Pty Ltd]:Purdue University
Organizational Unit Name (eg, section) []:OATS
Common Name (e.g. server FQDN or YOUR name) []:www.openatk.com
Email Address []:servio@palacios.com

Please enter the following 'extra' attributes
to be sent with your certificate request
A challenge password []:
An optional company name []:
OpenSSL> x509 -req -days 365 -in client.req -signkey client.key -out client.crt -extfile client.cnf -extensions ssl_client
Signature ok
subject=/C=US/ST=Indiana/L=West Lafayette/O=Purdue University/OU=OATS/CN=www.openatk.com/emailAddress=servio@palacios.com
Getting Private key
OpenSSL> pkcs12 -export -out client.pfx -inkey client.key -in client.crt
Enter Export Password:
Verifying - Enter Export Password:
OpenSSL> verify -X509_strict -purpose sslclient -CAfile client.crt client.crt
usage: verify [-verbose] [-CApath path] [-CAfile file] [-purpose purpose] [-crl_check] [-no_alt_chains] [-attime timestamp] [-engine e] cert1 cert2 ...
recognized usages:
        sslclient       SSL client
        sslserver       SSL server
        nssslserver     Netscape SSL server
        smimesign       S/MIME signing
        smimeencrypt    S/MIME encryption
        crlsign         CRL signing
        any             Any Purpose
        ocsphelper      OCSP helper
        timestampsign   Time Stamp signing
error in verify
OpenSSL> verify -x509_strict -purpose sslclient -CAfile client.crt client.crt
client.crt: OK
OpenSSL>
```
