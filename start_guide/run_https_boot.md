## Run HTTPS Boot {#run-https-boot}

Currently the UEFI HTTPS Boot feature only supports server authentication with an unauthenticated client. To support this mode, the Server CA certificate (rootcert.pem) is required by the Client. A private variable is used to configure the CA certificate on the client system. The EFI_SIGNATURE_LIST format is used for this variable:TlsCaCertificate, {0xfd2340D0, 0x3dab, 0x4349, {0xa6, 0xc7, 0x3b, 0x4f, 0x12, 0xb4, 0x8e, 0xae}}

### Configure the Certificate {#configure-the-certificate}

The server CA certificate must first be configured to enable UEFI HTTPS Boot. The TlsAuthConfigDxe driver provides a user interface to support the required certificate configuration. Figure 15 shows the UEFI Client configuration in Boot Manager.

Figure : UEFI Client Certificate Configuration

### Run HTTPS Boot on the UEFI Client {#run-https-boot-on-the-uefi-client}

After the Server CA certificate (rootcert.pem) has been configured, the NT32 simulator can perform a HTTPS Boot. Start the NT32 simulator, enter Boot Manager, and select “UEFI HTTPv4” or “UEFI HTTPv6” depending on the server configuration (see Figure 16).

Figure : Select Boot Option

During UEFI HTTPS Boot, the HttpDxe driver consumes the TlsDxe driver. This boot process supports HTTP and HTTPS, depending on the URL. This allows HttpDxe to communicate with an HTTPS or HTTP server configuration. The example in this document loads a UEFI Shell image downloaded from the server. Figure 17 shows the result of a successful UEFI HTTPS Boot.

Figure : Boot the Downloaded UEFI Shell Image