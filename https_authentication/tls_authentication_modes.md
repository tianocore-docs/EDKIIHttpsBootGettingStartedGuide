## TLS Authentication Modes {#tls-authentication-modes}

TLS supports three authentication modes:

1.  Two-way authentication: authentication of both parties. In this mode, both server and client will be authenticated.
2.  One-way authentication: server authentication with an unauthenticated client. That means only the server is authenticated by the client, and the client won’t be authenticated by the server.
3.  Total anonymity: the server and client won’t authenticate each other.

Table 1 shows the certificate requirement in each authentication mode for the HTTPS client and HTTPS server.

| Part Mode | Authentication of both parties | Server authentication with an unauthenticated client | Total anonymity |
| --- | --- | --- | --- |
| HTTPS Client | rootcert, clientcert, clientkey | Rootcert | NULL |
| HTTPS Server | rootcert, servercert, serverkey | servercert, serverkey | servercert, serverkey |

Table 1: Certificate Requirement