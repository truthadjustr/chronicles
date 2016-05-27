****
UNIX
****

The first creates a **self-signed** certificate, while the second creates a **CSR**:

    * openssl req -sha256 -new -x509 -key app.key.pem -out app.cert.pem    
    * openssl req -sha256 -new -key app.key.pem -out app.csr.pem

A *certificate* has already a date validity and expiration tagged into the certificate whereas a *CSR* does not have any concept of date validity and expiration yet.

A xxxx.p12 file is a cryptographic container file that can be password-protected. This file contains both the private & public keys and including the supporting
certificate chain of trusts.. To analyse this file,,

    * openssl pkcs12 -in xxxx.p12 -out xxxx.cert.pem -clcerts -nokeys <--- retrieve the certificate (and publick key)
    * openssl pkcs12 -in xxxx.p12 -out xxxx.privkey.pem -nocerts -nodes <--- retrieve the private key

The CRL can be downloaded from the certificate. But the CRL is in DER format. Convert to pem first:

    * openssl crl -inform DER -in crl.der -outform PEM -out crl.pem

And then read inside whose serial is expired:

    openssl crl -in crl.pem -noout -text


Get read / get the additional cert chain inside .p12:

    openssl pkcs12 -in path.p12 -out newfile.crt.pem -nokeys

..  toctree::
    :maxdepth: 2

    aix.rst    
    linux.rst
