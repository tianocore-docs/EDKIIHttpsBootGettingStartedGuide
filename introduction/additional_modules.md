## Additional Modules {#additional-modules}

All modules introduced in the EDK II HTTP Boot Getting Started Guide are necessary. HttpDxe driver needs to be updated to consume the TlsDxe driver.

The following new TLS modules are also required by HTTPS boot:

OpenSSL Crypto and TLS moduleCryptoPkg/Library/OpensslLib/OpensslLib.inf

Base Crypto LibraryCryptoPkg/Library/BaseCryptLib/BaseCryptLib.inf

TLS LibraryCryptoPkg/Library/TlsLib/TlsLib.inf

TLS DriverNetworkPkg/TlsDxe/TlsDxe.inf

TLS Authentication Config DriverNetworkPkg/TlsAuthConfigDxe/TlsAuthConfigDxe.inf