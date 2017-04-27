## Overview {#overview}

HTTP over TLS (HTTPS) boot is a standard implementation for securely booting using the Unified Extensible Firmware Interface (UEFI) over a network device. HTTPS Boot is especially important for clients using potentially insecure networks outside of corporate infrastructure. Security for UEFI HTTPS Boot is provided by the underlying Transport Layer Security (TLS).

UEFI HTTPS Boot is designed to overcome limitations of the [Preboot Execution Environment (PXE)](https://github.com/tianocore/tianocore.github.io/wiki/PXE) boot method currently supported by UEFI &amp; legacy BIOS firmware:

PXE uses UDP as transport layer protocol. TCP is not supported.

PXE is designed to work within a corporate network, not outside of a company firewall.

PXE uses TFTP and does not support a secure transport method (ex: HTTPS).

This document assumes that the reader is familiar with the EDK II HTTP Boot Getting Started Guide available on the [TianoCore whitepapers page](https://github.com/tianocore/tianocore.github.io/wiki/EDK%20II%20White%20papers). For information on configuring a HTTP Boot server, please refer to the [UEFI HTTP Boot with OVMF](https://en.opensuse.org/UEFI_HTTPBoot_with_OVMF) help page available at opensuse.org.