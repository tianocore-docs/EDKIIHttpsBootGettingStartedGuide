## Self-Generated Certificate {#self-generated-certificate}

This example shows how vendors can generate custom certificates for HTTPS Boot:

1.  Install OpenSSL.

Windows:

Download and install an [OpenSSL binary distribution](https://www.openssl.org/community/binaries.html). This document uses [Win32 OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) as an example.

Linux (Ubuntu as example):

sudo apt-get install openssl

1.  Create a self-signed CA Certificate:

openssl req -new -sha256 -keyout rootkey.pem -out rootreq.pem -days 3650

openssl x509 -req -in rootreq.pem -sha256 -signkey rootkey.pem -out rootcert.pem -days 3650

cat rootcert.pem rootkey.pem &gt; root.pem

(*Use type command instead of cat in Windows)

1.  Create a server certificate signed by the CA certificate:

openssl req -new -sha256 -keyout serverkey.pem -out serverreq.pem -days 3650

openssl x509 -req -in serverreq.pem -sha256 -CA root.pem -CAkey root.pem -CAcreateserial -out servercert.pem -days 3650

cat servercert.pem serverkey.pem root.pem &gt; server.pem

(*Use type command instead of cat in Windows)

openssl pkcs12 -export -in server.pem -out server.pfx

The .pem file is encoded as BASE64, but only PKCS12 format key can be used when booting to a Microsoft Windows server. This requires the last step in process above, converting server.pem to server.pfx.

1.  Create a client certificate signed by the CA certificate:

openssl req -new -sha256 -keyout clientkey.pem -out clientreq.pem -days 3650

openssl x509 -req -in clientreq.pem -sha256 -CA root.pem -CAkey root.pem -CAcreateserial -out clientcert.pem -days 3650

cat clientcert.pem clientkey.pem root.pem &gt; client.pem

(*Use type command instead of cat in Windows)

Using the steps above, the required key pairs are generated as shown in Table 2:

| CA | rootkey.pem, rootcert.pem, root.pem |
| --- | --- |
| Server | serverkey.pem, servercert.pem, server.pem, server.pfx |
| Client | clientkey.pem, clientcert.pem, client.pem |

Table 2: Key Pair

The next section demonstrates how to use ‘rootcert.pem’ and ‘server.pfx’ to enable server authentication with an unauthenticated client (one-way authentication).