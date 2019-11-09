# cedwards/base
Bastille Template: cedwards/base

## Usage:

```shell
bastille bootstrap https://github.com/cedwards/base
bastille template TARGET cedwards/base
```

## Template Overview

```shell
.
├── LICENSE
├── OVERLAY
├── PKG
├── README.md
├── SYSRC
├── etc
│   └── ssl
│       └── cert.pem -> /usr/local/share/certs/ca-root-nss.crt
├── root
│   └── .hushlogin
└── usr
    └── local
        ├── etc
        │   ├── pkg
        │   │   └── repos
        │   │       ├── BastilleBSD.conf
        │   │       └── FreeBSD.conf
        │   └── ssl
        │       ├── BastilleBSD.pub
        │       └── cert.pem.sample -> /usr/local/share/certs/ca-root-nss.crt
        ├── openssl
        │   └── cert.pem.sample -> /usr/local/share/certs/ca-root-nss.crt
        └── share
            ├── certs
            │   └── ca-root-nss.crt
            └── licenses
                └── ca_root_nss-3.47
                    ├── LICENSE
                    ├── MPL20
                    └── catalog.mk

14 directories, 16 files
```

This is a BastilleBSD template for my personal setup. This is applied to most
of my jailed systems, providing me with the baseline usability/comfort and
tools.


## Contents

### PKG
```shell
vim-console git-lite htop tree ca_root_nss
```

### SYSRC
```shell
cron_flags=-J 60
sendmail_enable=NONE
syslogd_flags=-ss
```

(These have become Bastille defaults so they might be redundant now.)

### OVERLAY
The overlay bootstraps my private repository, disables the upstream and also
pre-loads the latest `ca_root_nss` package contents. (certificate bootstrap
required to authenticate Let's Encrypt on my websites.

This also creates an empty `/root/.hushlogin` to silence all login messages.
