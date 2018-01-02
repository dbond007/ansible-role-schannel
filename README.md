SCHANNEL
========

Makes changes to SCHANNEL settings of the Windows
registry to serve more secure cryptographic
communications for services like IIS and winrm.

Ciphers:

* AES 128/128
* AES 256/256
* DES 56/56
* NULL
* RC2 40/128
* RC2 56/128
* RC2 128/128
* RC4 40/128
* RC4 56/128
* RC4 64/128
* RC4 128/128
* Triple DES 168/168

Protocols:

* PCT 1.0
* SSLv2
* SSLv3
* TLS 1.0
* TLS 1.1
* TLS 1.2

Hashes:

* MD5
* SHA-1
* SHA-256
* SHA-384
* SHA-512

Related documentation:

* [How to restrict the use of certain cryptographic algorithms and protocols in Schannel.dll](https://support.microsoft.com/en-us/help/245030/how-to-restrict-the-use-of-certain-cryptographic-algorithms-and-protocols-in-schannel.dll)
* [Schannel Security Support Provider Technical Reference: TLS/SSL Settings](https://technet.microsoft.com/en-us/library/dn786418.aspx)

Requirements
------------

Windows

Role Variables
--------------

Default values are as follows:

```
tls_3des: false
tls_aes_128: true
tls_aes_256: true
tls_des: false
tls_null: false
tls_rc2: false
tls_rc4: false

tls_md5: false
tls_sha1: false
tls_sha256: true
tls_sha384: true
tls_sha512: true

tls_pct: false
tls_sslv2: false
tls_sslv3: false
tls_tlsv10: false
tls_tlsv11: false
tls_tlsv12: true
```

Example Playbook
----------------

    - name: Harden Windows SCHANNEL configurations.
      hosts: windows2012

      vars:
        tls_tlsv10: true

      roles:
        - deekayen.schannel

Dependencies
------------

None.

License
-------

BSD 3-Clause License
