****
UNIX
****

The first creates a **self-signed** certificate, while the second creates a **CSR**:

    * openssl req -sha256 -new -x509 -key app.key.pem -out app.cert.pem    
    * openssl req -sha256 -new -key app.key.pem -out app.csr.pem

A *certificate* has already a date validity and expiration tagged into the certificate whereas a *CSR* does not have any concept of date validity and expiration yet.

..  toctree::
    :maxdepth: 2

    aix.rst    
    linux.rst
