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


## Run HTTPS Boot {#run-https-boot}

Currently the UEFI HTTPS Boot feature only supports server authentication with an unauthenticated client. To support this mode, the Server CA certificate (`rootcert.pem`) is required by the Client. A private variable is used to configure the CA certificate on the client system. The `EFI_SIGNATURE_LIST` format is used for this variable:`TlsCaCertificate, {0xfd2340D0, 0x3dab, 0x4349, {0xa6, 0xc7, 0x3b, 0x4f, 0x12, 0xb4, 0x8e, 0xae}}`

### Configure the Certificate {#configure-the-certificate}

The server CA certificate must first be configured to enable UEFI HTTPS Boot. The `TlsAuthConfigDxe` driver provides a user interface to support the required certificate configuration. Figure 15 shows the UEFI Client configuration in Boot Manager.
![](/media/image15.png)
######Figure 15: UEFI Client Certificate Configuration

### Run HTTPS Boot on the UEFI Client {#run-https-boot-on-the-uefi-client}

After the Server CA certificate (`rootcert.pem`) has been configured, the NT32 simulator can perform a HTTPS Boot. Start the NT32 simulator, enter Boot Manager, and select “UEFI HTTPv4” or “UEFI HTTPv6” depending on the server configuration (see Figure 16).
![](/media/image16.jpeg)
######Figure 16: Select Boot Option

During UEFI HTTPS Boot, the `HttpDxe` driver consumes the `TlsDxe` driver. This boot process supports HTTP and HTTPS, depending on the URL. This allows `HttpDxe` to communicate with an HTTPS or HTTP server configuration. The example in this document loads a UEFI Shell image downloaded from the server. Figure 17 shows the result of a successful UEFI HTTPS Boot.
![](/media/image17.jpeg)
######Figure 17: Boot the Downloaded UEFI Shell Image