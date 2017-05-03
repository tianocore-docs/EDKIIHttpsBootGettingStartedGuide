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

# HTTPS Authentication {#https-authentication}

Figure 1 shows the regular HTTPS authentication mechanism for both the server providing the boot image, and the client booting from the image. Leveraging an asymmetric crypto system, the client and server can be authenticated by each other. The steps for mutual authentication are as follows:

1.  Server and Client request the corresponding asymmetric key pair from the Certification Authority (CA). Both requested certificates can be verified by the CA.
2.  The CA distributes the key pair (`servercert/serverkey`) and its own certificate (`rootcert`) to the Server. The distributed certificate (servercert) has been signed by its rootkey.
3.  The CA distributes the key pair (`clientcert/clientkey`) and its own certificate (`rootcert`) to the Client. The distributed certificate (`clientcert`) has been signed by its rootkey.
4.  Both Server and Client present their own certificate to each other for mutual authentication.
5.  When the Server receives the Client certificate (`clientcert`) the certificate will be verified by rootcert, since it has been signed with the rootkey (and vice versa).


![](/media/image1.jpg)
###### Figure 1 Authentication Mechanism