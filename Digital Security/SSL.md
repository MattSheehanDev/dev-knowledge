
#macOS 

### Create a self-signed certificate
- Create self-signed certificate (pem/crt/cer) and private key
	- The `req` command creates and processes certificate requests in PKCS-10 format.
		- `-new` generates a new certificate request.
		- `-keyout` is the file to write the private key to.
		- `-x509` outputs a self-signed certificate instead of a certificate request. The default serial number used is 0, unless `-set_serial` is used.
```
openssl req -new -newkey rsa:2048 -keyout localhost.key -out localhost.cer -x509 -days 365 -subj /CN=localhost
```
- macOS has problems when two certificates are imported with the same CN (Comman Name).


#### Generate a PKCS-12 key
- PKCS-12 is a standard file format to store private keys together with their public keys.
		- PFX is Microsoft's implementation of this standard.
- The `pkcs12` command
	- `-export` option creates a PKCS-12 file.
	- `-inkey` is the private key to read from.
	- The password prompted for will be needed to re-export the certificate and key.
```
openssl pkcs12 -export -out certificate.pfx -inkey localhost.key -in localhost.cer
```

#### Parse PKCS-12 files
- Read a PKCS-12/PFX file
```
openssl pkcs12 -info -in pfxfile -nodes
```
- Output certificate file
```
openssl pkcs12 -in pfxfile -nodes -nokeys -out outfile.cer
```
- Output private key
```
openssl pkcs12 -in pfxfile -nodes -nocerts -out outfile.key
```

### Download an SSL Certificate

Get a site's SSL cert
- `s_client` is a generic SSL client utiltity
- The actual public cert is in X509 format and starts with `-----BEGIN CERTIFICATE-----` and ends with `-----END CERTIFICATE-----`
```
openssl s_client -connect <website>:443
```

Read and parse a public SSL cert
```
openssl x509 -in <cert-file> -text
```

### TODO

What is `security find-identity`



