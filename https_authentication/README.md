# HTTPS Authentication {#https-authentication}

Figure 1 shows the regular HTTPS authentication mechanism for both the server providing the boot image, and the client booting from the image. Leveraging an asymmetric crypto system, the client and server can be authenticated by each other. The steps for mutual authentication are as follows:

1.  Server and Client request the corresponding asymmetric key pair from the Certification Authority (CA). Both requested certificates can be verified by the CA.
2.  The CA distributes the key pair (servercert/serverkey) and its own certificate (rootcert) to the Server. The distributed certificate (servercert) has been signed by its rootkey.
3.  The CA distributes the key pair (clientcert/clientkey) and its own certificate (rootcert) to the Client. The distributed certificate (clientcert) has been signed by its rootkey.
4.  Both Server and Client present their own certificate to each other for mutual authentication.
5.  When the Server receives the Client certificate (clientcert) the certificate will be verified by rootcert, since it has been signed with the rootkey (and vice versa).

Figure : Authentication Mechanism