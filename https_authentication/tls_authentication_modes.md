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


## TLS Authentication Modes {#tls-authentication-modes}

TLS supports three authentication modes:

1.  Two-way authentication: authentication of both parties. In this mode, both server and client will be authenticated.
2.  One-way authentication: server authentication with an unauthenticated client. That means only the server is authenticated by the client, and the client won’t be authenticated by the server.
3.  Total anonymity: the server and client won’t authenticate each other.

Table 1 shows the certificate requirement in each authentication mode for the HTTPS client and HTTPS server.

| Part &#8594;<Br>---<br> Mode&#8595; | Authentication of both parties | Server authentication with an unauthenticated client | Total anonymity |
| --- | --- | --- | --- |
| HTTPS Client | rootcert, clientcert, clientkey | Rootcert | NULL |
| HTTPS Server | rootcert, servercert, serverkey | servercert, serverkey | servercert, serverkey |

######Table 1: Certificate Requirement