*****
REDIS
*****

Client stunnel's config::

    key = /tmp/stunnel/client.key.pem
    cert = /tmp/stunnel/client.cert.pem
    CAfile = /tmp/stunnel/chain-of-trust.pem
    verify = 2
    client = yes
    pid = /tmp/stunnel/stunnel.pid
    fips = no
    [redis]
    accept = 127.0.0.1:6379
    connect = 172.17.0.11:9379

Server stunnel's config::

    pid = /var/run/stunnel.pid
    verify = 2
    CAfile = /etc/stunnel/chain-of-trust.pem

    [redis]
    accept = 9379
    connect = 127.0.0.1:6379
    cert = /etc/stunnel/webdis.cert.pem
    key = /etc/stunnel/webdis.key.pem

..  toctree::
    :maxdepth: 2

    sentinel.rst
    clustering.rst
