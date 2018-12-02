# bastille-template-base
Bastille Template: Base

Usage:

```shell
bastille bootstrap https://github.com/cedwards/base
bastille template TARGET cedwards/base
```

## Template Overview

```shell
cedwards-base
├── CONFIG: 'etc root usr'
├── LICENSE: 'BSD 3-Clause License'
├── PKG: 'vim-console git-lite htop tree ca_root_nss'
├── README.md
├── SYSRC: 'cron_flags=-J 60, sendmail_enable=NONE, syslogd_flags=-ss'
├── etc
│   ├── hosts
│   └── ssl
│       └── cert.pem -> /usr/local/share/certs/ca-root-nss.crt
├── root
│   └── .hushlogin
└── usr
    └── local
        ├── etc
        │   ├── pkg
        │   │   └── repos
        │   │       ├── FreeBSD.conf
        │   │       └── BastilleBSD.conf
        │   └── ssl
        │       ├── cert.pem.sample -> /usr/local/share/certs/ca-root-nss.crt
        │       └── poudriere.pub
        ├── openssl
        │   └── cert.pem.sample -> /usr/local/share/certs/ca-root-nss.crt
        └── share
            ├── certs
            │   └── ca-root-nss.crt
            └── licenses
                └── ca_root_nss-3.40.1
                    ├── LICENSE
                    ├── MPL20
                    └── catalog.mk

```
