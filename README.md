<!--- @file
  README.md for EDK II Template Specification

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

<img src="media/TianocoreTitlePageLogo.jpg" width="300" />

# {{ book.title }}



** {{ gitbook.time|date('MM/DD/YYYY hh:mm:ss') }} **

{% if book.udkrelease %}
** {{ book.udkrelease }} **
{% endif %}

** {{ book.version }} **

#####WHITEPAPER

### Contributed by



Wu Jiaxin

Fu Siyuan

Brian Richardson

### Acknowledgements

Redistribution and use in source (original document form) and 'compiled'
forms (converted to PDF, epub, HTML and other formats) with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code (original document form) must retain the
   above copyright notice, this list of conditions and the following
   disclaimer as the first lines of this file unmodified.

2. Redistributions in compiled form (transformed to other DTDs, converted to
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

Copyright (c) 2017, Intel Corporation. All rights reserved.

### Revision History

| Revision   | Revision History   | Date        |
| ---------- | ------------------ | ----------- |
|  0.1  |       Initial release.                                                                                                                         | March 2016  |
|  0.2  |       Add UEFI Client Certificate Configuration                                                                                                | May 2016  |
|  0.3  |       Simplify the topology and configuration.                                                                                                 | May 2016  |
|  0.4  |       Refine the content                                                                                                                       | May 2016  |
|  0.5  |       Minor content revisions                                                                                           | May 2016  |
|  0.6  |       Updated figure references & document formatting. Text cleanup for information related to IPv4 & IPv6 configuration (multiple sections).  | June 2016  |
|  0.7  |       Modified document title. Added information on openSUSE implementation of HTTP Boot.                                                      | July 2016  |
|  0.8  |       Refine the contents.                                                                                                                     | Sep 2016  |
|  0.9  |       Update the certificate generation command for Windows OS                                                                                 | Sep 2016  |
|  1.0  |       Remove the consumed OpensslTlsLib module since the ssl building has been enabled in OpensslLib directly.                                 | Dec 2016  |
|  1.1  |       Minor formatting changes. Fixed hyperlinks to tianocore.org site and whitepapers.                                                        | Feb 2017  |
|  1.2  |       Add the IANA approved media type link. Specify the EDKII network stack version.            | Feb 2017  |
|  1.3  |       Replace examples of md5 signature algorithm with sha256. Added note on PXE to Overview Section with links to TianoCore wiki.       | Apr 2017  |


