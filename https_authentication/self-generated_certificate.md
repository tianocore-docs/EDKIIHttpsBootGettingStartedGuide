<!--- @file
  First Chapter of EDK II Template Specification

  Copyright (c) 2017, Intel Corporation. All rights reserved.<BR>

  Redistribution and use in source (original document form) and 'compiled'
  forms (converted to PDF, epub, HTML and other formats) with or without
  modification, are permitted provided that the following conditions are met:

  1) Redistributions of source code (original document form) must retain the
     above copyright notice, this list of conditions and the following
     disclaimer as the first lines of this file unmodified.

  2) Redistributions in compiled form (transformed to other DTDs, converted to
     PDF, epub, HTML and other formats) must reproduce the above copyright
     notice, this list of conditions and the following disclaimer in the
     documentation and/or other materials provided with the distribution.

  THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR
  IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
  MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
  EVENT SHALL TIANOCORE PROJECT  BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
  SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
  PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS;
  OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY,
  WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR
  OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF
  ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

-->


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