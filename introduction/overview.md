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


## Overview {#overview}

HTTP over TLS (HTTPS) boot is a standard implementation for securely booting using the Unified Extensible Firmware Interface (UEFI) over a network device. HTTPS Boot is especially important for clients using potentially insecure networks outside of corporate infrastructure. Security for UEFI HTTPS Boot is provided by the underlying Transport Layer Security (TLS).

UEFI HTTPS Boot is designed to overcome limitations of the [Preboot Execution Environment (PXE)](https://github.com/tianocore/tianocore.github.io/wiki/PXE) boot method currently supported by UEFI &amp; legacy BIOS firmware:

* PXE uses UDP as transport layer protocol. TCP is not supported.
* PXE is designed to work within a corporate network, not outside of a company firewall.
* PXE uses TFTP and does not support a secure transport method (ex: HTTPS).

This document assumes that the reader is familiar with the EDK II HTTP Boot Getting Started Guide available on the [TianoCore whitepapers page](https://github.com/tianocore/tianocore.github.io/wiki/EDK%20II%20White%20papers). For information on configuring a HTTP Boot server, please refer to the [UEFI HTTP Boot with OVMF](https://en.opensuse.org/UEFI_HTTPBoot_with_OVMF) help page available at opensuse.org.