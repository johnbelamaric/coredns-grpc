# grpc

This module enables a gRPC server for use with the proxy middleware, enabling
two CoreDNS instances to communicate via gRPC.

By default it will listen on port 80, or 443 if TLS is used.

## Syntax

~~~
grpc [ADDRESS]
~~~

Optionally takes an address; the default is `:80`, unless
tls is configured, in which case it is `:443`.

~~~
grpc [ADDRESS] {
	tls CERT KEY CA
}
~~~

## Examples

~~~
grpc
~~~

Enables cleartext gRPC listener on all addresses on port 80 (not recommended for production).

~~~
grpc {
	tls cert.pem key.pem ca.pem
}
~~~

Enables gRPC over TLS on port 443.
